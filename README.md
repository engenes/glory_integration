В 1С все товары нужны будет разбить по основным категориям. Внимание, это не разделы каталога!
Категории нужны только для того чтобы на сайте товары распределились по своим группам, у каждой группы товаров свой уникальный набор полей.
каждый товар должен иметь обязательный характеристики.

- availability - Наличие имеет 4 значения
1. 0 Нет в наличии
2. 1 Ожидает поступления
3. 2 Под заказ
4. 3 В наличии

- stock - Остаток. при остатке 0, не должно быть такого, что товар есть в наличии. Могу со своей стороны запрограммировать, чтобы при импорте, если у товара стоит статус есть в наличии но при этом остаток 0, то переводить "наличие" в состояние 0 - "нет в наличии", но любые проверки при обходе большого количества товаров - нагрузка на сервер.
Если можно автоматом еще в 1с ставить это поле в нет в наличии, когда остаток становится 0 было бы здорово. А они потом пусть сами меняют этот статус на любой другой, например под заказ или ожидает поступления

- status - Статус 0/1 - делает доступным товар для покупки, либо снимает его с публикации
- price - Цена
- sku  - Артикул (код товара, уникальное значение, использующееся в магазине для оформления заказа, и показывающееся посетителям)
- guid уникальный идентификатор сущности, необходимый для импорта
- updated - Дата обновления. Желательно UNIX формат, по дате обновления система будет понимать, нужно импортировать этот товар или пропустить.
- title - Заголовок товара

- product_type - тип товара (категория) через админку нельзя поменять категорию товара на любую другую, как я уже говорил, это самостоятельные сущности со своим набором полей.


1. acrylic                    | Акрил
2. auxiliary_liquids          | Вспомогательные жидкости
3. consumables                | Аксессуары и расходные материалы
4. depilation                 | Депиляция
5. design                     | Роспись и дизайн ногте
6. gels                       | Гели
7. gel_polishes               | Гель-лаки
8. hair_coloring              | Окрашивание волос
9. hair_cosmetics             | Косметика для волос
10. hair_tools                 | Инструменты для волос
11. hand_and_foot_care         | Уход за руками и ногами
12. hardware_manicure_pedicure | Приборы и оборудование
13. nail_decor                 | Декор ногтей
14. paraffin_therapy           | Парафинотерапия
15. starter_gif_sets           | Стартовые/подарочные наборы
16. sterilization              | Стерилизация
17. tools                      | Инструменты для маникюра и педикюра
18. yelashes_eyebrows          | Для ресниц и бровей

Ниже показал два способа, как можно передать данные

````{
    "sterilization": {//product_type
        "38B00F9B-916C-4AAA-B240-59E454A5F26E": { //guid
            "sku": "code-2zo8V",
            "title": "Продукт-12-34-тест",
            "price": 2333,
            "updated": 1612798319,
            "status": 1,
            "stock": 1,
            "availability": 2
        }
    },
    "gels": {
        "E5DEF0E2-4459-47D3-840A-EBC87C407188": {
            "sku": "code-zj6TE",
            "title": "Продукт-12-51-тест",
            "price": 2135,
            "updated": 1612798318,
            "status": 1,
            "stock": 78,
            "availability": 2
        },
        "D47BA661-F136-4944-9067-9D1A16943765": {
            "sku": "code-vvgGM",
            "title": "Продукт-9-1-тест",
            "price": 515,
            "updated": 1612798314,
            "status": 0,
            "stock": 87,
            "availability": 2
        },
        "1CC65CC1-F499-46D7-B885-10EBEC5858B0": {
            "sku": "code-EIdS8",
            "title": "Продукт-8-8-тест",
            "price": 2255,
            "updated": 1612798305,
            "status": 0,
            "stock": 39,
            "availability": 3
        },
        "A5B73E89-68E7-49A8-9C04-8D7CBB2340AA": {
            "sku": "code-VmQmN",
            "title": "Продукт-9-12-тест",
            "price": 1917,
            "updated": 1612798312,
            "status": 1,
            "stock": 64,
            "availability": 1
        },
        "6CDB8636-6F51-4A87-AB67-8AAF99DCAAF4": {
            "sku": "code-UVZth",
            "title": "Продукт-27-33-тест",
            "price": 1481,
            "updated": 1612798310,
            "status": 1,
            "stock": 70,
            "availability": 2
        },
        "548A4745-A37E-4121-95AB-DA1F022D3564": {
            "sku": "code-yZ8H1",
            "title": "Продукт-49-38-тест",
            "price": 2122,
            "updated": 1612798306,
            "status": 1,
            "stock": 75,
            "availability": 3
        }
    },
    "auxiliary_liquids": {
        "8EE079D4-1D2C-42BD-94F3-86351ACC4F1C": {
            "sku": "code-SJxHi",
            "title": "Продукт-50-32-тест",
            "price": 109,
            "updated": 1612798305,
            "status": 1,
            "stock": 62,
            "availability": 1
        },
        "908653D5-083F-4460-BBFD-DA96D722826A": {
            "sku": "code-XsnYQ",
            "title": "Продукт-35-44-тест",
            "price": 127,
            "updated": 1612798315,
            "status": 1,
            "stock": 54,
            "availability": 3
        },
        "39AF2362-16CB-4956-A000-E793FCC02E86": {
            "sku": "code-gDWoe",
            "title": "Продукт-53-35-тест",
            "price": 1989,
            "updated": 1612798307,
            "status": 1,
            "stock": 16,
            "availability": 2
        },
        "8F51E433-4AC2-48D3-97A9-3E7ADEFC60A6": {
            "sku": "code-ybimU",
            "title": "Продукт-11-17-тест",
            "price": 1038,
            "updated": 1612798315,
            "status": 1,
            "stock": 24,
            "availability": 1
        }
    },
    "hardware_manicure_pedicure": {
        "B51B1228-5B0C-43E6-9866-084B1B862305": {
            "sku": "code-8fMOX",
            "title": "Продукт-6-4-тест",
            "price": 785,
            "updated": 1612798314,
            "status": 1,
            "stock": 59,
            "availability": 2
        },
        "533B7E01-63CD-43FD-A51E-20362BC502C0": {
            "sku": "code-206l5",
            "title": "Продукт-14-27-тест",
            "price": 2062,
            "updated": 1612798317,
            "status": 1,
            "stock": 36,
            "availability": 3
        },
        "0E9C3C12-B8DA-42A7-8856-A75C14CA0933": {
            "sku": "code-8FhYz",
            "title": "Продукт-11-42-тест",
            "price": 2424,
            "updated": 1612798315,
            "status": 1,
            "stock": 97,
            "availability": 3
        },
        "8FCF2068-9E5C-4213-BD1E-87842AA36B36": {
            "sku": "code-1Z4rp",
            "title": "Продукт-2-52-тест",
            "price": 2334,
            "updated": 1612798305,
            "status": 1,
            "stock": 11,
            "availability": 3
        }
    },
    "nail_decor": {
        "D798FF8C-E509-4AF5-8719-4D204CEC4929": {
            "sku": "code-4N8xJ",
            "title": "Продукт-7-34-тест",
            "price": 1127,
            "updated": 1612798309,
            "status": 1,
            "stock": 20,
            "availability": 1
        },
        "B89078CD-A450-4A5C-8B76-DC3292197AC6": {
            "sku": "code-Nz3xb",
            "title": "Продукт-55-8-тест",
            "price": 2442,
            "updated": 1612798310,
            "status": 1,
            "stock": 77,
            "availability": 3
        },
        "37611B17-4497-4617-9480-1F3F6D3FCCF7": {
            "sku": "code-J103w",
            "title": "Продукт-22-4-тест",
            "price": 960,
            "updated": 1612798307,
            "status": 1,
            "stock": 85,
            "availability": 1
        },
        "3B66B0E8-FA56-4BF3-918E-4DB087DBB5B7": {
            "sku": "code-9G3IS",
            "title": "Продукт-12-19-тест",
            "price": 2403,
            "updated": 1612798311,
            "status": 1,
            "stock": 40,
            "availability": 1
        }
    },
    "hair_tools": {
        "33336515-1245-41CA-A60A-1A0959C32002": {
            "sku": "code-l1VrZ",
            "title": "Продукт-46-2-тест",
            "price": 721,
            "updated": 1612798309,
            "status": 1,
            "stock": 46,
            "availability": 1
        },
        "F5E82C60-9448-4ECC-A93F-D3BC09A1397F": {
            "sku": "code-BCrzZ",
            "title": "Продукт-50-19-тест",
            "price": 1142,
            "updated": 1612798309,
            "status": 1,
            "stock": 20,
            "availability": 3
        },
        "E888ADFD-CC07-46BC-9578-B2807D32D057": {
            "sku": "code-m2836",
            "title": "Продукт-33-17-тест",
            "price": 1950,
            "updated": 1612798318,
            "status": 1,
            "stock": 19,
            "availability": 2
        },
        "46836739-C7AD-477A-AC3B-B3F731B5A54D": {
            "sku": "code-koT0r",
            "title": "Продукт-1-21-тест",
            "price": 736,
            "updated": 1612798309,
            "status": 1,
            "stock": 63,
            "availability": 3
        }
    },
    "tools": {
        "485D5373-CD74-46C5-91CB-A8852366BB56": {
            "sku": "code-AFmtl",
            "title": "Продукт-19-54-тест",
            "price": 2027,
            "updated": 1612798307,
            "status": 1,
            "stock": 80,
            "availability": 1
        },
        "F2368F0A-8E8C-46EE-9083-424F925BF148": {
            "sku": "code-oz0cn",
            "title": "Продукт-45-10-тест",
            "price": 1224,
            "updated": 1612798319,
            "status": 1,
            "stock": 10,
            "availability": 3
        },
        "6F498770-E90A-4AE1-93A1-BDA50BBF5FF5": {
            "sku": "code-dwNrT",
            "title": "Продукт-38-3-тест",
            "price": 1740,
            "updated": 1612798317,
            "status": 1,
            "stock": 46,
            "availability": 2
        },
        "63AE85C0-990D-4812-B9E2-36638A17DD20": {
            "sku": "code-vKoo4",
            "title": "Продукт-24-25-тест",
            "price": 756,
            "updated": 1612798307,
            "status": 1,
            "stock": 11,
            "availability": 1
        },
        "A5EA3FD5-041C-4EAF-83BA-0158CF23D443": {
            "sku": "code-gXMzd",
            "title": "Продукт-55-36-тест",
            "price": 1351,
            "updated": 1612798313,
            "status": 1,
            "stock": 82,
            "availability": 1
        }
    },
    "depilation": {
        "A134CCE1-CCE3-418D-A1E9-A51FA753A45D": {
            "sku": "code-clYbv",
            "title": "Продукт-38-21-тест",
            "price": 2309,
            "updated": 1612798314,
            "status": 1,
            "stock": 34,
            "availability": 2
        },
        "BA0A5653-5E50-459B-B448-50D9251D40F6": {
            "sku": "code-89gBS",
            "title": "Продукт-47-9-тест",
            "price": 1345,
            "updated": 1612798318,
            "status": 1,
            "stock": 80,
            "availability": 3
        },
        "D1B7AC64-0A90-4799-84D9-D5AFFA6116AB": {
            "sku": "code-ZzHC1",
            "title": "Продукт-16-24-тест",
            "price": 1359,
            "updated": 1612798316,
            "status": 1,
            "stock": 44,
            "availability": 1
        }
    },
    "gel_polishes": {
        "8C9DC13F-4C6E-43F3-9CDD-0DF5B5250439": {
            "sku": "code-aytvN",
            "title": "Продукт-22-1-тест",
            "price": 1185,
            "updated": 1612798315,
            "status": 1,
            "stock": 77,
            "availability": 2
        },
        "E92929DF-A6E3-45D4-95A9-8AA46F0CE27F": {
            "sku": "code-y0ZwN",
            "title": "Продукт-48-17-тест",
            "price": 2348,
            "updated": 1612798317,
            "status": 1,
            "stock": 1,
            "availability": 2
        }
    },
    "hair_coloring": {
        "019F070D-3B02-442F-A769-817911E16CC1": {
            "sku": "code-rAF6U",
            "title": "Продукт-35-29-тест",
            "price": 1407,
            "updated": 1612798308,
            "status": 1,
            "stock": 50,
            "availability": 3
        },
        "6A6E5762-3773-442F-9456-C28EB0E4560E": {
            "sku": "code-ADBvj",
            "title": "Продукт-41-31-тест",
            "price": 213,
            "updated": 1612798304,
            "status": 1,
            "stock": 37,
            "availability": 1
        },
        "13FBFD54-F575-4256-9299-5B3661058DFF": {
            "sku": "code-bch9R",
            "title": "Продукт-36-12-тест",
            "price": 265,
            "updated": 1612798317,
            "status": 1,
            "stock": 82,
            "availability": 3
        }
    },
    "acrylic": {
        "DE8D74E1-F893-49A9-BF28-166D5D97014E": {
            "sku": "code-fr9Z6",
            "title": "Продукт-1-37-тест",
            "price": 1348,
            "updated": 1612798314,
            "status": 1,
            "stock": 7,
            "availability": 1
        },
        "33651981-F142-4412-9398-E930D2D55C15": {
            "sku": "code-rWxnP",
            "title": "Продукт-26-9-тест",
            "price": 2142,
            "updated": 1612798308,
            "status": 1,
            "stock": 74,
            "availability": 2
        }
    },
    "consumables": {
        "C01AC8FD-2146-48E6-8676-F9B786223B77": {
            "sku": "code-DUbu6",
            "title": "Продукт-36-18-тест",
            "price": 1859,
            "updated": 1612798318,
            "status": 1,
            "stock": 79,
            "availability": 3
        },
        "25DF23E2-AA79-4C8F-9B94-85559ACF8306": {
            "sku": "code-Gxxaf",
            "title": "Продукт-27-12-тест",
            "price": 1873,
            "updated": 1612798319,
            "status": 1,
            "stock": 6,
            "availability": 2
        }
    },
    "starter_gif_sets": {
        "81669335-71AB-432C-B7AF-FE823601AE4A": {
            "sku": "code-vnhaj",
            "title": "Продукт-0-31-тест",
            "price": 2441,
            "updated": 1612798308,
            "status": 1,
            "stock": 66,
            "availability": 2
        },
        "FD273FC4-0690-465A-81AF-E7F826CBCE48": {
            "sku": "code-rro4X",
            "title": "Продукт-40-14-тест",
            "price": 146,
            "updated": 1612798307,
            "status": 1,
            "stock": 38,
            "availability": 3
        }
    },
    "hair_cosmetics": {
        "A7ADD088-E8D8-422A-93F5-8C599DB365E2": {
            "sku": "code-fvEe1",
            "title": "Продукт-47-3-тест",
            "price": 2197,
            "updated": 1612798319,
            "status": 1,
            "stock": 85,
            "availability": 1
        },
        "C9DEF1BA-7122-42D5-B128-34F563F2AB11": {
            "sku": "code-kUAXy",
            "title": "Продукт-19-43-тест",
            "price": 1140,
            "updated": 1612798318,
            "status": 1,
            "stock": 36,
            "availability": 2
        },
        "9FECF37D-E116-4798-B43B-B367BCD21896": {
            "sku": "code-Sd5tT",
            "title": "Продукт-21-31-тест",
            "price": 880,
            "updated": 1612798304,
            "status": 1,
            "stock": 87,
            "availability": 2
        }
    },
    "design": {
        "1B37B3C7-B2D6-439A-A033-7A5F5F9BA77F": {
            "sku": "code-Wx7vc",
            "title": "Продукт-54-8-тест",
            "price": 281,
            "updated": 1612798318,
            "status": 1,
            "stock": 16,
            "availability": 2
        }
    },
    "yelashes_eyebrows": {
        "52E09AFE-EF52-4CA2-9C71-14C387C514D3": {
            "sku": "code-ou1mI",
            "title": "Продукт-33-29-тест",
            "price": 2395,
            "updated": 1612798308,
            "status": 1,
            "stock": 6,
            "availability": 3
        }
    },
    "paraffin_therapy": {
        "BFAED8B8-8821-406D-9594-CEAD64290634": {
            "sku": "code-pUr0b",
            "title": "Продукт-21-34-тест",
            "price": 2357,
            "updated": 1612798319,
            "status": 1,
            "stock": 90,
            "availability": 3
        },
        "3FFF2D8F-3E61-4A33-ACE7-E3041C6998A9": {
            "sku": "code-03FFX",
            "title": "Продукт-13-14-тест",
            "price": 1054,
            "updated": 1612798313,
            "status": 1,
            "stock": 60,
            "availability": 2
        },
        "17749A21-444B-4641-B6DA-661FB5559206": {
            "sku": "code-9YRph",
            "title": "Продукт-17-12-тест",
            "price": 1411,
            "updated": 1612798314,
            "status": 0,
            "stock": 62,
            "availability": 3
        }
    }
}

Если не получится в таком виде, то можно собрать просто плоский масссив

[
    {
        "sku": "code-S0mfD",
        "product_type": "paraffin_therapy",
        "guid": "C524DF59-F295-45E4-A434-6207F93D9BC5",
        "title": "Продукт-5-6-тест",
        "price": 1075,
        "updated": 1612798743,
        "status": 1,
        "stock": 73,
        "availability": 1
    },
    {
        "sku": "code-48viV",
        "product_type": "design",
        "guid": "C4ACE721-9388-483B-8E19-2ADB69226819",
        "title": "Продукт-17-53-тест",
        "price": 2066,
        "updated": 1612798739,
        "status": 1,
        "stock": 47,
        "availability": 1
    },
    {
        "sku": "code-k7jdG",
        "product_type": "sterilization",
        "guid": "DD484DCF-25EA-4FD2-B4F6-D0EB17D9CB5F",
        "title": "Продукт-1-48-тест",
        "price": 717,
        "updated": 1612798741,
        "status": 1,
        "stock": 25,
        "availability": 2
    },
    {
        "sku": "code-0RB5j",
        "product_type": "hardware_manicure_pedicure",
        "guid": "E67EE92A-5F3D-41B2-8808-88ADCC74B838",
        "title": "Продукт-41-26-тест",
        "price": 855,
        "updated": 1612798739,
        "status": 1,
        "stock": 35,
        "availability": 1
    },
    {
        "sku": "code-DAIwN",
        "product_type": "design",
        "guid": "8C713DE7-560F-4642-9A27-C76021579198",
        "title": "Продукт-36-43-тест",
        "price": 834,
        "updated": 1612798738,
        "status": 1,
        "stock": 61,
        "availability": 1
    },
    {
        "sku": "code-PzGWp",
        "product_type": "consumables",
        "guid": "B3E28041-B379-4004-ADCA-511449234AF0",
        "title": "Продукт-12-47-тест",
        "price": 1171,
        "updated": 1612798738,
        "status": 1,
        "stock": 76,
        "availability": 3
    },
    {
        "sku": "code-9yiS6",
        "product_type": "tools",
        "guid": "0F839AF3-72F7-465E-82DE-DBE82B0D2684",
        "title": "Продукт-8-51-тест",
        "price": 1371,
        "updated": 1612798744,
        "status": 1,
        "stock": 39,
        "availability": 2
    },
    {
        "sku": "code-AvzLy",
        "product_type": "gel_polishes",
        "guid": "B475CFF6-AB6D-42F4-9350-985194D588EE",
        "title": "Продукт-10-2-тест",
        "price": 1098,
        "updated": 1612798741,
        "status": 1,
        "stock": 66,
        "availability": 3
    },
    {
        "sku": "code-yYUXp",
        "product_type": "yelashes_eyebrows",
        "guid": "3BC87029-387B-42FC-9EF7-57E0E2EECE38",
        "title": "Продукт-2-1-тест",
        "price": 623,
        "updated": 1612798745,
        "status": 1,
        "stock": 17,
        "availability": 2
    },
    {
        "sku": "code-hhQGN",
        "product_type": "depilation",
        "guid": "5BFA2AD4-1BF0-4015-BDD7-4082A90FB922",
        "title": "Продукт-43-5-тест",
        "price": 528,
        "updated": 1612798739,
        "status": 1,
        "stock": 44,
        "availability": 2
    },
    {
        "sku": "code-BbCAM",
        "product_type": "yelashes_eyebrows",
        "guid": "097C323A-13BF-493D-8BBB-69B4C22B7226",
        "title": "Продукт-15-38-тест",
        "price": 1732,
        "updated": 1612798741,
        "status": 0,
        "stock": 91,
        "availability": 1
    },
    {
        "sku": "code-qf5zM",
        "product_type": "hair_coloring",
        "guid": "C1B54BC0-5C49-4895-95E3-11F710C6A5D3",
        "title": "Продукт-10-26-тест",
        "price": 2103,
        "updated": 1612798735,
        "status": 1,
        "stock": 30,
        "availability": 1
    },
    {
        "sku": "code-D20tA",
        "product_type": "hand_and_foot_care",
        "guid": "B07D67FC-069E-4277-B611-077337EACF46",
        "title": "Продукт-43-25-тест",
        "price": 1899,
        "updated": 1612798737,
        "status": 1,
        "stock": 98,
        "availability": 3
    },
    {
        "sku": "code-QDcR5",
        "product_type": "hair_cosmetics",
        "guid": "1110D440-F7F2-4FBB-BCFF-94B6F8D52959",
        "title": "Продукт-37-21-тест",
        "price": 1023,
        "updated": 1612798737,
        "status": 1,
        "stock": 35,
        "availability": 3
    },
    {
        "sku": "code-VQdtS",
        "product_type": "hair_coloring",
        "guid": "616205C5-3AAC-4B70-A4AF-E3354B5E9657",
        "title": "Продукт-21-28-тест",
        "price": 1165,
        "updated": 1612798739,
        "status": 1,
        "stock": 30,
        "availability": 3
    },
    {
        "sku": "code-67OZY",
        "product_type": "hair_tools",
        "guid": "4420E918-3009-44CF-AFE0-2D0F2BEF9E99",
        "title": "Продукт-46-30-тест",
        "price": 2072,
        "updated": 1612798735,
        "status": 0,
        "stock": 14,
        "availability": 2
    },
    {
        "sku": "code-xXZNc",
        "product_type": "hair_tools",
        "guid": "9032019A-E075-488D-B491-D23EA6C7B508",
        "title": "Продукт-16-10-тест",
        "price": 2212,
        "updated": 1612798743,
        "status": 1,
        "stock": 50,
        "availability": 3
    },
    {
        "sku": "code-BDOXu",
        "product_type": "hair_cosmetics",
        "guid": "594A3003-ADEA-4AE7-93FE-6B9FCE1E56CA",
        "title": "Продукт-9-19-тест",
        "price": 695,
        "updated": 1612798749,
        "status": 1,
        "stock": 80,
        "availability": 1
    },
    {
        "sku": "code-BryZn",
        "product_type": "design",
        "guid": "1CDD7EE9-CBA0-4F92-B0F5-18EB2798BE5D",
        "title": "Продукт-45-44-тест",
        "price": 723,
        "updated": 1612798746,
        "status": 1,
        "stock": 58,
        "availability": 3
    },
    {
        "sku": "code-q4PZH",
        "product_type": "yelashes_eyebrows",
        "guid": "F2726593-51D7-4284-A59E-E036E7455236",
        "title": "Продукт-40-31-тест",
        "price": 1967,
        "updated": 1612798741,
        "status": 1,
        "stock": 94,
        "availability": 2
    },
    {
        "sku": "code-l9Yrq",
        "product_type": "depilation",
        "guid": "7448C5BD-1FEB-4FEF-A82E-9E64E3891B98",
        "title": "Продукт-19-8-тест",
        "price": 2141,
        "updated": 1612798739,
        "status": 1,
        "stock": 25,
        "availability": 1
    },
    {
        "sku": "code-iVOg1",
        "product_type": "starter_gif_sets",
        "guid": "80B239E0-087D-4241-AE29-4ACA40502D82",
        "title": "Продукт-15-15-тест",
        "price": 1390,
        "updated": 1612798748,
        "status": 1,
        "stock": 81,
        "availability": 2
    },
    {
        "sku": "code-UeZ3o",
        "product_type": "hair_coloring",
        "guid": "89E80518-0214-44B0-8BB7-A11DFC983C26",
        "title": "Продукт-53-36-тест",
        "price": 2291,
        "updated": 1612798749,
        "status": 1,
        "stock": 94,
        "availability": 1
    },
    {
        "sku": "code-5Nv0R",
        "product_type": "paraffin_therapy",
        "guid": "932C93AB-28E4-4BE7-BA8A-F6D5F95047C6",
        "title": "Продукт-36-26-тест",
        "price": 1697,
        "updated": 1612798738,
        "status": 1,
        "stock": 29,
        "availability": 2
    },
    {
        "sku": "code-KNnkZ",
        "product_type": "yelashes_eyebrows",
        "guid": "3EEC6E82-DF49-42B8-A1EA-4A08B2A52061",
        "title": "Продукт-18-19-тест",
        "price": 1839,
        "updated": 1612798736,
        "status": 1,
        "stock": 15,
        "availability": 1
    },
    {
        "sku": "code-1Bj43",
        "product_type": "gels",
        "guid": "8806A822-F372-4C5C-9339-1AD9364D9EB6",
        "title": "Продукт-40-23-тест",
        "price": 1451,
        "updated": 1612798746,
        "status": 1,
        "stock": 20,
        "availability": 1
    },
    {
        "sku": "code-UkYKm",
        "product_type": "paraffin_therapy",
        "guid": "0F7807D0-FA4E-484E-B968-50F48AEFAA22",
        "title": "Продукт-7-24-тест",
        "price": 2207,
        "updated": 1612798748,
        "status": 1,
        "stock": 91,
        "availability": 3
    },
    {
        "sku": "code-7J1Hy",
        "product_type": "auxiliary_liquids",
        "guid": "72EF8E42-4E0C-4D50-9467-CB1559B3AFE7",
        "title": "Продукт-13-7-тест",
        "price": 499,
        "updated": 1612798748,
        "status": 1,
        "stock": 68,
        "availability": 1
    },
    {
        "sku": "code-fOD4I",
        "product_type": "sterilization",
        "guid": "6A4B5FC7-C1B6-4467-86F0-BD97FD477595",
        "title": "Продукт-35-10-тест",
        "price": 2118,
        "updated": 1612798750,
        "status": 1,
        "stock": 3,
        "availability": 2
    },
    {
        "sku": "code-IwE0C",
        "product_type": "auxiliary_liquids",
        "guid": "5F959236-F6F6-4F22-84C2-B7EB4E3B0B15",
        "title": "Продукт-40-11-тест",
        "price": 2412,
        "updated": 1612798747,
        "status": 1,
        "stock": 16,
        "availability": 3
    },
    {
        "sku": "code-VzFzQ",
        "product_type": "gel_polishes",
        "guid": "4D2ADFE2-95A0-49DB-8F27-1BD7B58321A1",
        "title": "Продукт-23-50-тест",
        "price": 1598,
        "updated": 1612798738,
        "status": 1,
        "stock": 3,
        "availability": 2
    },
    {
        "sku": "code-2EaV0",
        "product_type": "hair_coloring",
        "guid": "651910E7-5DBD-4ABF-9C27-F319BE2C2D18",
        "title": "Продукт-9-45-тест",
        "price": 540,
        "updated": 1612798738,
        "status": 1,
        "stock": 19,
        "availability": 2
    },
    {
        "sku": "code-PApyF",
        "product_type": "auxiliary_liquids",
        "guid": "00777788-5987-4E6D-AC5D-68613EA17E8D",
        "title": "Продукт-8-20-тест",
        "price": 1422,
        "updated": 1612798747,
        "status": 1,
        "stock": 30,
        "availability": 1
    },
    {
        "sku": "code-BqhN1",
        "product_type": "yelashes_eyebrows",
        "guid": "617E7F10-D5D1-48C2-B458-64766291A3D9",
        "title": "Продукт-8-18-тест",
        "price": 1243,
        "updated": 1612798739,
        "status": 1,
        "stock": 88,
        "availability": 3
    },
    {
        "sku": "code-YiXOL",
        "product_type": "starter_gif_sets",
        "guid": "DA1900E6-09D9-4064-B884-25901468F8A7",
        "title": "Продукт-19-26-тест",
        "price": 2369,
        "updated": 1612798749,
        "status": 1,
        "stock": 54,
        "availability": 3
    },
    {
        "sku": "code-2OTye",
        "product_type": "gels",
        "guid": "CBBED8DF-BC16-41D2-B1EE-7A5BFF7A2F8C",
        "title": "Продукт-11-52-тест",
        "price": 1947,
        "updated": 1612798736,
        "status": 1,
        "stock": 77,
        "availability": 1
    },
    {
        "sku": "code-hW74s",
        "product_type": "gels",
        "guid": "E9732D7E-987F-4F64-A8FA-EC7DA20434A6",
        "title": "Продукт-23-44-тест",
        "price": 814,
        "updated": 1612798741,
        "status": 1,
        "stock": 46,
        "availability": 2
    },
    {
        "sku": "code-FywPU",
        "product_type": "acrylic",
        "guid": "CEC5D8C2-593F-49C6-B208-6852325F2CC4",
        "title": "Продукт-34-24-тест",
        "price": 1397,
        "updated": 1612798739,
        "status": 1,
        "stock": 38,
        "availability": 3
    },
    {
        "sku": "code-tJpwQ",
        "product_type": "yelashes_eyebrows",
        "guid": "E95938DA-F37F-4EA9-9D88-D5817A7C09B3",
        "title": "Продукт-7-0-тест",
        "price": 1538,
        "updated": 1612798750,
        "status": 1,
        "stock": 66,
        "availability": 2
    },
    {
        "sku": "code-5Cjgr",
        "product_type": "nail_decor",
        "guid": "8CB4C180-A7A2-4D0E-BBBE-8EF6D11E83F4",
        "title": "Продукт-23-23-тест",
        "price": 762,
        "updated": 1612798745,
        "status": 1,
        "stock": 13,
        "availability": 1
    },
    {
        "sku": "code-PRyO0",
        "product_type": "depilation",
        "guid": "D3F59156-5D70-409A-9111-DD431C2587C8",
        "title": "Продукт-16-28-тест",
        "price": 475,
        "updated": 1612798746,
        "status": 1,
        "stock": 70,
        "availability": 2
    },
    {
        "sku": "code-grFmH",
        "product_type": "hair_tools",
        "guid": "1BECB50B-248F-4812-A63A-0125A6C29F9B",
        "title": "Продукт-37-6-тест",
        "price": 1405,
        "updated": 1612798739,
        "status": 1,
        "stock": 55,
        "availability": 1
    },
    {
        "sku": "code-isNRN",
        "product_type": "consumables",
        "guid": "29D71920-BBA8-4DD5-9D66-EA741825910C",
        "title": "Продукт-19-30-тест",
        "price": 184,
        "updated": 1612798747,
        "status": 1,
        "stock": 53,
        "availability": 2
    },
    {
        "sku": "code-U7Xs6",
        "product_type": "acrylic",
        "guid": "91207D1A-096F-4CAB-ABA9-C2CE0127E512",
        "title": "Продукт-31-39-тест",
        "price": 1762,
        "updated": 1612798736,
        "status": 1,
        "stock": 24,
        "availability": 3
    },
    {
        "sku": "code-pOjFa",
        "product_type": "yelashes_eyebrows",
        "guid": "1933D2B3-0801-4ECD-B0F7-DAA0ACA54E96",
        "title": "Продукт-49-26-тест",
        "price": 1684,
        "updated": 1612798745,
        "status": 1,
        "stock": 94,
        "availability": 2
    },
    {
        "sku": "code-5Sq4j",
        "product_type": "paraffin_therapy",
        "guid": "8A93C082-B8D1-4944-B083-4D70E68799B0",
        "title": "Продукт-13-10-тест",
        "price": 2340,
        "updated": 1612798738,
        "status": 0,
        "stock": 91,
        "availability": 1
    },
    {
        "sku": "code-ii125",
        "product_type": "acrylic",
        "guid": "5BE76B94-8361-4FAA-97D2-742FEFA1244B",
        "title": "Продукт-23-11-тест",
        "price": 1502,
        "updated": 1612798749,
        "status": 1,
        "stock": 85,
        "availability": 2
    },
    {
        "sku": "code-xVlvi",
        "product_type": "acrylic",
        "guid": "ECFF3E99-0BCD-4B66-8120-33C293F45ECE",
        "title": "Продукт-16-21-тест",
        "price": 270,
        "updated": 1612798737,
        "status": 1,
        "stock": 34,
        "availability": 1
    },
    {
        "sku": "code-uk7fA",
        "product_type": "consumables",
        "guid": "8A05E108-1370-4299-8C6A-229DDDC567B0",
        "title": "Продукт-50-17-тест",
        "price": 352,
        "updated": 1612798744,
        "status": 1,
        "stock": 8,
        "availability": 2
    },
    {
        "sku": "code-qM5l1",
        "product_type": "nail_decor",
        "guid": "40ABCB6C-84A6-4DC3-826F-D8CDC54C0F97",
        "title": "Продукт-52-11-тест",
        "price": 1232,
        "updated": 1612798742,
        "status": 1,
        "stock": 35,
        "availability": 3
    }
]

