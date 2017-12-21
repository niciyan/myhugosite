---
title: "Second"
date: 2017-12-20T21:21:35+09:00
draft: false
---

Today, I will show you some my old story. It's a boring and keeping you sleppy.
good .  

Golang Snippet.  

		package main

		import (
			"encoding/json"
			"fmt"
			"github.com/jinzhu/gorm"
			_ "github.com/jinzhu/gorm/dialects/mysql"
		)

		type Product struct {
			gorm.Model
			Code  string
			Price uint
		}

		type User struct {
			gorm.Model
			Emails []Email
			Name   string
		}

		type Email struct {
			gorm.Model
			Email  string
			UserID uint
		}

		func main() {
			db, err := gorm.Open("mysql", "root@/rem?charset=utf8&parseTime=True&loc=Local")
			if err != nil {
				panic("failed to connect database")
			}
			defer db.Close()

			// Migrate the schema
			db.AutoMigrate(&User{}, &Email{})
			// db.Model(&user).Related(&emails)

			var user = User{
				Name: "Nishi",
			}
			db.Create(&user)

			// Create
			db.Create(&Product{Code: "L1212", Price: 1000})

			// Read
			var product Product
			db.First(&product, 1)                   // find product with id 1
			db.First(&product, "code = ?", "L1212") // find product with code l1212
			db.Find(&product)

			data, err := json.MarshalIndent(&product, "", "    ")
			if err != nil {
				fmt.Println("error occured while marshalling product object.", err)
				return
			}

			fmt.Println(string(data))

			// Update - update product's price to 2000
			db.Model(&product).Update("Price", 2000)

			// Delete - delete product
			db.Delete(&product)
		}
