# API Response Documentation

Bu doküman, her API endpoint'i için örnek yanıtları içermektedir. Yanıtlar JSON formatındadır ve açıklamalarla birlikte verilmiştir.

## 1. publisher-performance-api

**Endpoint:** `GET /api/publisher-performance?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için yayınevlerinin performans verilerini döndürür.

**Örnek Yanıt:**
```json
{
  "publishers": [
    {
      "name": "Acil Yayınları",
      "target": 3789456,
      "achieved": 1789456,
      "percentage": 47.22
    },
    {
      "name": "Apotemi Yayınları",
      "target": 3789456,
      "achieved": 2789456,
      "percentage": 73.61
    }
  ]
}
```

## 2. product-category-performance-api

**Endpoint:** `GET /api/product-category-performance?branch_id=123&level=lise`

**Açıklama:** Bu API, belirli bir şube ve eğitim seviyesi için ürün kategorilerinin performans verilerini döndürür.

**Örnek Yanıt:**
```json
{
  "categories": [
    {
      "name": "Soru Bankası",
      "target": 10987,
      "achieved": 8452,
      "percentage": 76.93
    },
    {
      "name": "Fasikül/Defter",
      "target": 10987,
      "achieved": 7654,
      "percentage": 69.66
    }
  ]
}
```

## 3. product-detail-breakdown-api

**Endpoint:** `GET /api/product-detail-breakdown?branch_id=123&category=soru_bankasi`

**Açıklama:** Bu API, belirli bir şube ve ürün kategorisi için ürün detaylarını döndürür.

**Örnek Yanıt:**
```json
{
  "products": [
    {
      "name": "TYT Matematik Soru Bankası",
      "class": "TYT",
      "subject": "Matematik",
      "quantity": 120987
    },
    {
      "name": "AYT Fizik Soru Bankası",
      "class": "AYT",
      "subject": "Fizik",
      "quantity": 98765
    }
  ]
}
```

## 4. branch_summary_api

**Endpoint:** `GET /api/branch-summary?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için özet bilgileri döndürür.

**Örnek Yanıt:**
```json
{
  "total_target": 345567,
  "total_achieved": 245567,
  "overall_percentage": 71.06,
  "total_revenue": 3789093.12
}
```

## 5. top-bottom-books-api

**Endpoint:** `GET /api/top-bottom-books?branch_id=123&limit=2`

**Açıklama:** Bu API, belirli bir şube için en çok ve en az satan kitapların listesini döndürür.

**Örnek Yanıt:**
```json
{
  "top_books": [
    {
      "name": "TYT Matematik Soru Bankası",
      "quantity": 130923
    },
    {
      "name": "AYT Fizik Soru Bankası",
      "quantity": 100923
    }
  ],
  "bottom_books": [
    {
      "name": "11. Sınıf Kimya Fasikülü",
      "quantity": 34
    },
    {
      "name": "9. Sınıf Biyoloji Defteri",
      "quantity": 190
    }
  ]
}
```

## 6. all-publisher-chart-api

**Endpoint:** `GET /api/all-publisher-chart?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için tüm yayınevlerinin satış verilerini döndürür, genellikle grafik oluşturmak için kullanılır.

**Örnek Yanıt:**
```json
{
  "publishers": [
    {
      "name": "Acil Yayınları",
      "sales": 87654
    },
    {
      "name": "Apotemi Yayınları",
      "sales": 76543
    },
    {
      "name": "Bilgi Sarmal Yayınları",
      "sales": 65432
    }
  ]
}
```

## 7. publisher_distribution_api

**Endpoint:** `GET /api/publisher-distribution?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için yayınevlerinin satış dağılımını yüzdelik olarak döndürür.

**Örnek Yanıt:**
```json
{
  "distribution": [
    {
      "name": "Acil Yayınları",
      "percentage": 35
    },
    {
      "name": "Apotemi Yayınları",
      "percentage": 30
    },
    {
      "name": "Bilgi Sarmal Yayınları",
      "percentage": 20
    },
    {
      "name": "Diğer",
      "percentage": 15
    }
  ]
}
```

Not: Tüm API çağrılarında `branch_id` parametresi zorunludur ve ilgili şubenin verilerini filtrelemek için kullanılır.
