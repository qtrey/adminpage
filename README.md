<!DOCTYPE html>A
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">
  <title>Admin Page</title>
</head>
<body>
  <div class="container mt-3">
    <h3 class="mt-5 mb-3">신규 등록 상품</h3>
    <form class="row row-cols-lg-auto g-3 align-items-center">      
      <div class="col-12">
        <label class="visually-hidden" for="inlineFormSelectPref">Preference</label>
        <select class="form-select" id="inlineFormSelectPref" name="category_data_table">
          <!-- 셀렉트요소의 name="category_data_table"은 지우거나 변경하면 안돼요 -->
          <!-- 카테고리 셀렉트 코드를 넣어주세요 -->
          <div class="mb-3">
            <label for="category" class="form-label">카테고리 선택:</label>
            <select id="category" class="form-select">
                <option value="">카테고리를 선택하세요</option>
                <option value="상의">상의</option>
                <option value="하의">하의</option>
                <option value="신발">신발</option>
                <option value="패션잡화">패션잡화</option>
        </select>
      </div>
      <div class="col-3">
        <!-- input 입력창 코드를 넣어주세요 -->
        <div class="input-group mb-4">
            <input type="text" class="form-control" placeholder="제품명을 입력해주세요" aria-label="제품명 검색">
            <button class="btn btn-primary">조회</button>
        </div>
      </div>
      <div class="col-auto">
        <!-- 조회 버튼 코드를 넣어주세요 -->
      </div>
    </form>

    <div class="container mt-3">
      <table class="table table-sm">
        <thead>
          <!-- 열의 속성값을 나타내는 코드를 작성해주세요 (예 : 카테고리, 브랜드, 상품명, 가격) -->
        </thead>
        <tbody id="product_data_Table">
          <!-- tbody요소의 id="product_data_Table" 는 지우거나 변경하면 안돼요! -->
          <!-- 제품 데이터가 여기 추가됩니다. -->
        </tbody>
      </table>
    </div>
    <!-- 페이지 네이션 코드를 넣어주세요 -->
  </div>

  <script>
    // 크롤링한 데이터를 아래와 같은 형태의 객체 배열로 가정합니다.
    // 추후 데이터베이스에 있는 데이터를 쿼리문으로 불러 올 수 있게 쿼리를 작성해 볼 수 있음

    // 제품 데이터
    const product_data = [
      { category: "상의", brand: 'Supreme', product: '슈프림 박스로고 후드티', price: '390,000' },
      { category: "하의", brand: 'DIESEL', product: '디젤 트랙 팬츠', price: '188,000' },
      { category: "신발", brand: 'Nike', product: '에어포스 1', price: '137,000' },
      { category: "패션잡화", brand: 'Music&Goods', product: '빵빵이 키링', price: '29,000' },
      // ...
    ];

    // 제품 테이블에 데이터 추가
    const product_data_Table = document.getElementById('product_data_Table');

    // 초기 데이터 로딩
    product_data.forEach((item) => {
      const row = product_data_Table.insertRow();
      row.insertCell(0).innerHTML = item.category;
      row.insertCell(1).innerHTML = item.brand;
      row.insertCell(2).innerHTML = item.product;
      row.insertCell(3).innerHTML = item.price;
    });
  </script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
