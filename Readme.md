# seller.py 
В двух словах что делает:
ЭТО скрипт для работы с маркетплейсами Озон и Casio:
получает список товаров из Озон и формирует список их артикулов;
скачивает с сайта Casio список остатков часов;
обновляет информацию о ценах и количестве имеющихся на складе часов на Озон.
[Требуется уникальные значения ID продавца для Ozon](https://sellerstats.ru/help/api_key_ozon)



get_product_list(last_id, client_id, seller_token):
Получить список товаров магазина озон c количеством меньше 1000

get_offer_ids(client_id, seller_token)
Получить артикулы товаров магазина озон

update_price(prices: list, client_id, seller_token):
Обновить цены товаров

update_stocks(stocks: list, client_id, seller_token)
Обновить остатки

download_stock():
Скачать файл ostatki с сайта casio "https://timeworld.ru/upload/files/ostatki.zip"
Создаем список остатков часов:
результат в  "ostatki.xls"

def create_stocks(watch_remnants, offer_ids):
Уберем то, что не загружено в seller
Добавим недостающее из загруженного:
возвращаем stocks

create_prices(watch_remnants, offer_ids):
создаем цены не заморачиваясь 

price_conversion(price: str) -> str:
Преобразовать цену в нужный формат

def divide(lst: list, n: int)
Разделить список lst на части по n элементов

upload_prices(watch_remnants, client_id, seller_token):
создаем прайс

upload_stocks(watch_remnants, client_id, seller_token):
создаем список товаров

main()
Обновить остатки
Поменять цены



# market.py
В двух словах что делает:
Это скрипт работы с маркетплейсами Yandex и Casio по моделям FBS и DBS

скачивает с сайта Casio список остатков часов
для каждой модели работы:
получает список товаров из Yandex маркета и формирует список их артикулов;
обновляет информацию о ценах и количестве имеющихся на складе часов на Yandex.

get_product_list(page, campaign_id, access_token)
Получить список товаров из Yandex с лимитом 200

update_stocks(stocks, campaign_id, access_token):
Обновить остатки товаров на Yandex


def update_price(prices, campaign_id, access_token):
Обновить цены товаров на Yandex
возвращает типа цены response_object = response.json()

get_offer_ids(campaign_id, market_token)
Получить артикулы товаров Яндекс маркета"

create_stocks(watch_remnants, offer_ids, warehouse_id)
Уберем то, что не загружено в market
Возвращает список текущих остатков, с учетом часов, отсутствующих у Casio, но имеющихся на Yandex

create_prices(watch_remnants, offer_ids)
Создает цены товаров, загруженных с Casio
prices список текущих цен часов, совпадающих с размещенными на Yandex

upload_prices(watch_remnants, campaign_id, market_token):
Получение арктикулов и обновление цен часов на Yandex
return prices

upload_stocks(watch_remnants, campaign_id, market_token, warehouse_id)
Получает арктикли обновления остатков часов на Yandex

main()
Обновить остатки FBS
Поменять цены FBS
Обновить остатки DBS
Поменять цены DBS
    
