# Güncellenmiş API Yanıt Dokümantasyonu (TypeScript Types ile)

## 1. branch-summary-api

**Endpoint:** `GET /api/branch-summary?branch_id=123`

**TypeScript Types:**
```typescript
type BranchSummary = {
  genel: SummaryData;
  lise: SummaryData;
  ortaokul: SummaryData;
  basari_durumu: {
    yuzde: number;
    mesaj: string;
  };
  tarih: string;
};

type SummaryData = {
  toplam_hedef: {
    adet: number;
    tutar: number;
  };
  gerceklesen_hedef: {
    adet: number;
    tutar: number;
  };
  gerceklesme_orani: number;
};
```

## 2. top-bottom-books-api

**Endpoint:** `GET /api/top-bottom-books?branch_id=123&limit=5`

**TypeScript Types:**
```typescript
type TopBottomBooks = {
  top_books: BookData[];
  bottom_books: BookData[];
};

type BookData = {
  name: string;
  quantity: number;
};
```

## 3. all-publisher-chart-api

**Endpoint:** `GET /api/all-publisher-chart?branch_id=123`

**TypeScript Types:**
```typescript
type PublisherChartData = {
  publishers: PublisherSales[];
};

type PublisherSales = {
  name: string;
  sales: number;
};
```

## 4. publisher-distribution-api

**Endpoint:** `GET /api/publisher-distribution?branch_id=123`

**TypeScript Types:**
```typescript
type PublisherDistribution = {
  distribution: PublisherPercentage[];
};

type PublisherPercentage = {
  name: string;
  percentage: number;
};
```

## 5. publisher-performance-api

**Endpoint:** `GET /api/publisher-performance?branch_id=123`

**TypeScript Types:**
```typescript
type PublisherPerformance = {
  publishers: PublisherData[];
};

type PublisherData = {
  name: string;
  target: number;
  achieved: number;
  percentage: number;
};
```

## 6. product-category-performance-api

**Endpoint:** `GET /api/product-category-performance?branch_id=123`

**TypeScript Types:**
```typescript
type ProductCategoryPerformance = {
  lise: CategoryPerformance;
  ortaokul: CategoryPerformance;
};

type CategoryPerformance = {
  categories: CategoryData[];
};

type CategoryData = {
  name: string;
  target: number;
  achieved: number;
  percentage: number;
};
```

## 7. product-detail-breakdown-api

**Endpoint:** `GET /api/product-detail-breakdown?branch_id=123&category=soru_bankasi&level=lise`

**TypeScript Types:**
```typescript
type ProductDetailBreakdown = {
  products: ProductDetail[];
};

type ProductDetail = {
  name: string;
  class: string;
  subject: string;
  quantity: number;
};
```

Not: Tüm API çağrılarında `branch_id` parametresi zorunludur ve ilgili şubenin verilerini filtrelemek için kullanılır.
