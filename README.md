# Güncellenmiş API Yanıt Dokümantasyonu

Bu doküman, her API endpoint'i için güncellenmiş örnek yanıtları içermektedir. Yanıtlar JSON formatındadır ve açıklamalarla birlikte verilmiştir.

## 1. branch-summary-api

**Endpoint:** `GET /api/branch-summary?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için özet bilgileri döndürür.



**Örnek Yanıt:**
```json
{
  "genel": {
    "toplam_hedef": {
      "adet": 345567.00,
      "tutar": 345567.00
    },
    "gerceklesen_hedef": {
      "adet": 245567.00,
      "tutar": 245567.00
    },
    "gerceklesme_orani": 87
  },
  "lise": {
    "toplam_hedef": {
      "adet": 345567.00,
      "tutar": 345567.00
    },
    "gerceklesen_hedef": {
      "adet": 245567.00,
      "tutar": 245567.00
    },
    "gerceklesme_orani": 87
  },
  "ortaokul": {
    "toplam_hedef": {
      "adet": 345567.00,
      "tutar": 345567.00
    },
    "gerceklesen_hedef": {
      "adet": 245567.00,
      "tutar": 245567.00
    },
    "gerceklesme_orani": 87
  },
  "basari_durumu": {
    "yuzde": 87,
    "mesaj": "Eksik olduğunuz yayınları inceleyerek başarınızı arttırabilirsiniz."
  },
  "tarih": "01.07.2024"
}
```

**Dipnot:** 
Bu örnekte, `basari_durumu.mesaj` alanı artık zengin içerik (rich content) formatında sunulmaktadır. Bu format, istemci uygulamasının mesajı daha zengin ve etkileşimli bir şekilde göstermesine olanak tanır. İçerik, başlıklar, paragraflar, listeler ve hatta butonlar gibi farklı elementler içerebilir. İstemci uygulaması, bu yapıyı kullanarak kullanıcı arayüzünde daha görsel ve etkileşimli bir deneyim sunabilir.

Zengin içerik formatı, uygulamanın farklı platformlarda (web, mobil, tablet vb.) tutarlı bir görünüm sağlamasına yardımcı olur ve gelecekte yeni içerik türleri eklemeyi kolaylaştırır. Ayrıca, bu yapı sayesinde sunucu tarafında mesaj içeriğini dinamik olarak oluşturmak ve kişiselleştirmek mümkün hale gelir.

**Örnek Yanıt:**
```json
{
  .....
  },
  "basari_durumu": {
    "yuzde": 87,
    "mesaj": {
      "type": "rich_content",
      "content": [
        {
          "type": "header",
          "text": "Tebrikler! Başarı Oranınız %87",
          "style": "h2",
          "color": "#4CAF50"
        },
        {
          "type": "paragraph",
          "text": "Hedefinize yaklaşmak üzeresiniz. İşte size önerilerimiz:",
          "style": "normal"
        },
        {
          "type": "list",
          "style": "unordered",
          "items": [
            "Eksik olduğunuz yayınları inceleyerek başarınızı arttırabilirsiniz.",
            "Özellikle ortaokul kategorisinde hedeflerinizi gözden geçirin.",
            "En çok satan ürünlerinize odaklanarak satışlarınızı artırın."
          ]
        },
        {
          "type": "button",
          "text": "Detaylı Raporu Görüntüle",
          "url": "/detailed-report",
          "style": "primary"
        }
      ]
    }
  },
  "tarih": "01.07.2024"
}
```

## 2. top-bottom-books-api

**Endpoint:** `GET /api/top-bottom-books?branch_id=123&limit=5`

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
    },
    {
      "name": "9. Sınıf Türkçe Kitabı",
      "quantity": 95000
    },
    {
      "name": "8. Sınıf İnkılap Tarihi",
      "quantity": 92000
    },
    {
      "name": "11. Sınıf Kimya",
      "quantity": 88000
    }
  ],
  "bottom_books": [
    {
      "name": "11. Sınıf Almanca Çalışma Kitabı",
      "quantity": 34
    },
    {
      "name": "9. Sınıf Biyoloji Defteri",
      "quantity": 190
    },
    {
      "name": "12. Sınıf Felsefe Kitabı",
      "quantity": 250
    },
    {
      "name": "10. Sınıf Coğrafya Atlası",
      "quantity": 300
    },
    {
      "name": "7. Sınıf Sosyal Bilgiler Defteri",
      "quantity": 350
    }
  ]
}
```

## 3. all-publisher-chart-api

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
    },
    {
      "name": "Palme Yayınları",
      "sales": 54321
    },
    {
      "name": "Karekök Yayınları",
      "sales": 43210
    }
  ]
}
```

## 4. publisher-distribution-api

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
      "name": "Palme Yayınları",
      "percentage": 10
    },
    {
      "name": "Diğer",
      "percentage": 5
    }
  ]
}
```

## 5. publisher-performance-api

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
    },
    {
      "name": "Bilgi Sarmal Yayınları",
      "target": 3789456,
      "achieved": 3334521,
      "percentage": 87.98
    },
    {
      "name": "Palme Yayınları",
      "target": 3789456,
      "achieved": 3000000,
      "percentage": 79.17
    }
  ]
}
```

## 6. product-category-performance-api

**Endpoint:** `GET /api/product-category-performance?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için hem lise hem de ortaokul seviyesinde ürün kategorilerinin performans verilerini döndürür.

**Örnek Yanıt:**
```json
{
  "lise": {
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
      },
      {
        "name": "Deneme",
        "target": 10987,
        "achieved": 9123,
        "percentage": 83.03
      },
      {
        "name": "Diğer",
        "target": 10987,
        "achieved": 6789,
        "percentage": 61.79
      }
    ]
  },
  "ortaokul": {
    "categories": [
      {
        "name": "Soru Bankası",
        "target": 9876,
        "achieved": 7654,
        "percentage": 77.50
      },
      {
        "name": "Fasikül/Defter",
        "target": 9876,
        "achieved": 8765,
        "percentage": 88.75
      },
      {
        "name": "Deneme",
        "target": 9876,
        "achieved": 8234,
        "percentage": 83.37
      },
      {
        "name": "Diğer",
        "target": 9876,
        "achieved": 7123,
        "percentage": 72.12
      }
    ]
  }
}
```

## 7. product-detail-breakdown-api

**Endpoint:** `GET /api/product-detail-breakdown?branch_id=123&category=soru_bankasi&level=lise`

**Açıklama:** Bu API, belirli bir şube, kategori ve eğitim seviyesi için ürün detaylarını döndürür.

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
    },
    {
      "name": "11. Sınıf Kimya Soru Bankası",
      "class": "11. Sınıf",
      "subject": "Kimya",
      "quantity": 87654
    },
    {
      "name": "9. Sınıf Biyoloji Soru Bankası",
      "class": "9. Sınıf",
      "subject": "Biyoloji",
      "quantity": 76543
    }
  ]
}
```

Not: Tüm API çağrılarında `branch_id` parametresi zorunludur ve ilgili şubenin verilerini filtrelemek için kullanılır.


# Complete Branch API Documentation

## complete-branch-api

**Endpoint:** `GET /api/complete-branch?branch_id=123`

**Açıklama:** Bu API, belirli bir şube için tüm verileri tek bir çağrıda döndürür. Bu, diğer tüm API'lerin verilerini birleştirir.

**TypeScript Type:**
```typescript
type CompleteBranchData = {
  summary: BranchSummary;
  topBottomBooks: TopBottomBooks;
  publisherChart: PublisherChartData;
  publisherDistribution: PublisherDistribution;
  publisherPerformance: PublisherPerformance;
  productCategoryPerformance: ProductCategoryPerformance;
};
```

**Örnek Yanıt:**
```json
{
  "summary": {
    "genel": {
      "toplam_hedef": {
        "adet": 345567.00,
        "tutar": 345567.00
      },
      "gerceklesen_hedef": {
        "adet": 245567.00,
        "tutar": 245567.00
      },
      "gerceklesme_orani": 87
    },
    "lise": {
      "toplam_hedef": {
        "adet": 345567.00,
        "tutar": 345567.00
      },
      "gerceklesen_hedef": {
        "adet": 245567.00,
        "tutar": 245567.00
      },
      "gerceklesme_orani": 87
    },
    "ortaokul": {
      "toplam_hedef": {
        "adet": 345567.00,
        "tutar": 345567.00
      },
      "gerceklesen_hedef": {
        "adet": 245567.00,
        "tutar": 245567.00
      },
      "gerceklesme_orani": 87
    },
    "basari_durumu": {
      "yuzde": 87,
      "mesaj": {
        "type": "rich_content",
        "content": [
          {
            "type": "header",
            "text": "Tebrikler! Başarı Oranınız %87",
            "style": "h2",
            "color": "#4CAF50"
          },
          {
            "type": "paragraph",
            "text": "Hedefinize yaklaşmak üzeresiniz. İşte size önerilerimiz:",
            "style": "normal"
          },
          {
            "type": "list",
            "style": "unordered",
            "items": [
              "Eksik olduğunuz yayınları inceleyerek başarınızı arttırabilirsiniz.",
              "Özellikle ortaokul kategorisinde hedeflerinizi gözden geçirin.",
              "En çok satan ürünlerinize odaklanarak satışlarınızı artırın."
            ]
          },
          {
            "type": "button",
            "text": "Detaylı Raporu Görüntüle",
            "url": "/detailed-report",
            "style": "primary"
          }
        ]
      }
    },
    "tarih": "01.07.2024"
  },
  "topBottomBooks": {
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
        "name": "11. Sınıf Almanca Çalışma Kitabı",
        "quantity": 34
      },
      {
        "name": "9. Sınıf Biyoloji Defteri",
        "quantity": 190
      }
    ]
  },
  "publisherChart": {
    "publishers": [
      {
        "name": "Acil Yayınları",
        "sales": 87654
      },
      {
        "name": "Apotemi Yayınları",
        "sales": 76543
      }
    ]
  },
  "publisherDistribution": {
    "distribution": [
      {
        "name": "Acil Yayınları",
        "percentage": 35
      },
      {
        "name": "Apotemi Yayınları",
        "percentage": 30
      }
    ]
  },
  "publisherPerformance": {
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
  },
  "productCategoryPerformance": {
    "lise": {
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
    },
    "ortaokul": {
      "categories": [
        {
          "name": "Soru Bankası",
          "target": 9876,
          "achieved": 7654,
          "percentage": 77.50
        },
        {
          "name": "Fasikül/Defter",
          "target": 9876,
          "achieved": 8765,
          "percentage": 88.75
        }
      ]
    }
  }
}
```

**Not:** Bu API, diğer tüm API'lerin verilerini tek bir çağrıda döndürür. Bu, ağ trafiğini azaltabilir ve uygulama performansını artırabilir, ancak büyük miktarda veri döndürdüğü için yüklenme süresi uzayabilir. Kullanım senaryonuza bağlı olarak, bu API'yi veya ayrı API'leri kullanmayı tercih edebilirsiniz.
