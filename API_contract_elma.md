
Метод: POST
Адрес: https://elma365dev.mriya.me/pub/v1/bpm/template/departments.supplier_requests/order_status_supplier_update/run
Body:
{
  "context": {
    "request_data": (тип: строка) [ JSON с Интерфейсом IRequestData ],
  }
}

==================================================================================

/** Данные по одной потребности */
interface INeedData {
    /** Наименование */
    name: string,
    /** Количество */
    count: number,
    /** Единица измерения */
    measurement_unit: string,
    /** Цена (тариф) за единицу измерения */
    price_for_measurement_unit: number,
    /** Ставка НДС */
    vat_rate: string,
    /** Сумма с НДС */
    price_with_vat: number,
    /** UID 1C Склад получателя */
    warehouse_receiver_uid: string
    /** GUID 1C номенклатурной позиции */
    nomenclature_uid: string
}

/** Формат входного JSON */
interface IRequestData {
    /** UID ELMA Заказ поставщику */
    request_id: string,
    /** Данные потребностей */
    need_data: INeedData[]
}

======================================================================

ПРИМЕР ЗАПРОСА

{
      "context": {
        "request_data": "{\"request_id\":\"019f27ec-d745-7450-bb68-8b3208d574f8\",\"need_data\":[{\"name\":\"Адаптер питания сетевой Apple USB-C 61W\",\"count\":1,\"measurement_unit\":\"шт\",\"price_for_measurement_unit\":1000,\"vat_rate\":\"20%\",\"price_with_vat\":1200,\"warehouse_receiver_uid\":\"50a990ea-b4fe-11e9-80df-000c29589659\",\"nomenclature_uid\":\"487e5f38-64cd-11ed-825a-000c29589659\"}]}"
      }
    }