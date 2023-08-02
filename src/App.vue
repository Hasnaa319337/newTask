<template>
  <div style="margin: 10px 0" class="global">
    <div class="container overflow-hidden">
      <!-- Start:: Cards -->
      <div class="row g-2" style="direction: rtl">
        <div class="col col-lg-3 col-md-6 col-sm-12 global_div" v-for="div in divs" :key="div">
          <div class="p-3">
            <h3 class="global_head">{{ div.head }}</h3>
            <span class="global_span">{{ div.num }}</span>
          </div>
        </div>
      </div>
      <!-- End: Cards -->

      <!-- Start:: Filter -->
      <div class="row g-2" style="direction: rtl; margin-top: 20px">
        <div
          class="col col-lg-3 col-md-6 col-sm-4"
          style="display: flex; justify-content: center; align-items: center"
        >
          <h3 class="global_head" style="font-size:22px">الشكاوي الجديدة</h3>
        </div>
        <div class="col col-lg-3 col-md-6 col-sm-4" v-for="filter in filters" :key="filter">
          <div class="p-3">
            <span class="filter_span">{{ filter.title }}</span>

            <!-- Start :: DropDown -->
            <div class="dropdown" style="display: inline">
              <button
                class="btn btn-secondary dropdown-toggle"
                type="button"
                id="dropdownMenuButton2"
                data-bs-toggle="dropdown"
                aria-expanded="false"
                style="
                  background-color: #e7fff3;
                  border: none;
                  color: #000;
                  outline: none;
                  width: 200px;
                  text-align: start;
                "
              >
                الكل
              </button>
              <ul class="dropdown-menu dropdown-menu-dark" aria-labelledby="dropdownMenuButton2">
                <li><a class="dropdown-item active" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
                <li><hr class="dropdown-divider" /></li>
                <li><a class="dropdown-item" href="#">Separated link</a></li>
              </ul>
            </div>
            <!-- End:: DropDown -->
          </div>
        </div>
      </div>
      <!-- End:: Filter -->

      <!-- Start:: Tabel -->
      <div class="table-responsive">
        <table class="table">
          <thead class="thead" style="background: red !important">
            <tr>
              <th v-for="head in thead" :key="head">
                {{ head }}
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="body in dataBody" :key="body">
              <td class="serial">{{ body.id }}</td>
              <td>{{ body.type }}</td>
              <td>{{ body.date }}</td>
              <td>{{ body.city }}</td>
              <td>{{ body.adminstration }}</td>
              <td class="status">{{ body.status }}</td>
              <td class="icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="16"
                  height="16"
                  fill="currentColor"
                  class="bi bi-eye"
                  viewBox="0 0 16 16"
                >
                  <path
                    d="M16 8s-3-5.5-8-5.5S0 8 0 8s3 5.5 8 5.5S16 8 16 8zM1.173 8a13.133 13.133 0 0 1 1.66-2.043C4.12 4.668 5.88 3.5 8 3.5c2.12 0 3.879 1.168 5.168 2.457A13.133 13.133 0 0 1 14.828 8c-.058.087-.122.183-.195.288-.335.48-.83 1.12-1.465 1.755C11.879 11.332 10.119 12.5 8 12.5c-2.12 0-3.879-1.168-5.168-2.457A13.134 13.134 0 0 1 1.172 8z"
                  />
                  <path
                    d="M8 5.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5zM4.5 8a3.5 3.5 0 1 1 7 0 3.5 3.5 0 0 1-7 0z"
                  />
                </svg>
              </td>
            </tr>
          </tbody>
          <div></div>
        </table>
      </div>
      <!-- End:: Tabel -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      divs: [
        { head: 'شكاوي جديدة', num: 150 },
        { head: 'شكاوي تم اعتمادها', num: 150 },
        { head: 'الشكاوي المرفوضة', num: 44 },
        { head: 'الشكاوي المرفوضة', num: 44 }
      ],
      filters: [{ title: 'التاريخ' }, { title: 'التصنيف' }, { title: 'الحالة' }],
      thead: ['رقم الشكوي', 'نوع الشكوي', 'تاريخ الشكوي', 'المدينة', 'الادارة', 'الحالة', 'عرض'],
      dataBody: [
        {
          id: 1,
          type: 'شكوى 1',
          date: 'مايو ,4 ,2023',
          city: 'الرياض',
          adminstration: 'ادارة الشكاوي',
          status: 'تم قبولها',
          show: 'icon'
        },
        {
          id: 2,
          type: 'شكوى 1',
          date: 'مايو ,4 ,2023',
          city: 'الرياض',
          adminstration: 'ادارة الشكاوي',
          status: 'تم قبولها',
          show: 'icon'
        },
        {
          id: 3,
          type: 'شكوى 1',
          date: 'مايو ,4 ,2023',
          city: 'الرياض',
          adminstration: 'ادارة الشكاوي',
          status: 'تم قبولها',
          show: 'icon'
        },
        {
          id: 4,
          type: 'شكوى 1',
          date: 'مايو ,4 ,2023',
          city: 'الرياض',
          adminstration: 'ادارة الشكاوي',
          status: 'تم قبولها',
          show: 'icon'
        },
        {
          id: 5,
          type: 'شكوى 1',
          date: 'مايو ,4 ,2023',
          city: 'الرياض',
          adminstration: 'ادارة الشكاوي',
          status: 'تم قبولها',
          show: 'icon'
        }
      ]
    }
  }
}
</script>

<style>
@import url(https://db.onlinewebfonts.com/c/d11e9f3094b83670e2094a780c2e4f2e?family=Tajawal);

.global {
  font-family: 'Tajawal';
  font-size: 18px;
}
.global_div div {
  padding: 22px 76px;
  border-radius: 14px;
  color: #fff;
  text-align: center;
}
.global_div:nth-of-type(1) div {
  background: #fdbe7b;
}
.global_div:nth-of-type(2) div {
  background: #12aa77;
}
.global_div:nth-of-type(3) div {
  background: #ff6a6f;
}
.global_div:nth-of-type(4) div {
  background: #43a7d8;
}
.global_head {
  font-size: 24px;
  font-weight: 500;
}
.global_span {
  font-size: 32px;
  font-weight: 700;
}

.table {
  direction: rtl;
  text-align: center;
  margin: 50px 0;
}

.table .thead tr th {
  background: #33835c !important;
  color: #fff !important;
  border: none;
  font-size: 20px;
  font-weight: 500;
  padding: 7px 0;
  line-height: 39px;
  padding-bottom: 10px;
}
.table tbody tr td {
  padding: 17px 0 !important;
  border: none;
}
.table tbody tr:first-of-type {
  border-bottom: 2px solid #ddd;
}
.table tbody tr:nth-of-type(4) {
  border-bottom: 2px solid #ddd;
}
.table tbody tr:last-of-type {
  border-bottom: 1px solid #656565;
}
.table tbody tr:nth-of-type(3) {
  background: #f6f6f6 !important;
}
.serial {
  font-weight: 700 !important;
}

.status {
  color: #ffab5f !important;
}
.icon {
  cursor: pointer;
}
.filter_span {
  color: #00000078;
  font-size: 17px;
  margin: 0 6px;
  font-weight: 500;
}

/* Start Filter */
.btn:focus {
  border: none;

  outline: none;
}

.dropdown-toggle::after {
  display: inline-block;
  margin-left: 0.255em;
  vertical-align: 0.255em;
  content: '';
  border-top: 0.3em solid;
  text-align: end;
  border-right: 0.3em solid transparent;
  border-bottom: 0;
  border-left: 0.3em solid transparent;
  float: left;
  margin-top: 10px;
}
/* End Filter */
</style>
