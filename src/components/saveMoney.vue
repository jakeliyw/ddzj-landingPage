<template>
  <div>
    <img
      src="../assets/image/header_img.png"
      alt="头部广告"
      class="header_img"
    />
    <div class="layout">
      <div class="popular_Leasing_layout">
        <div class="popular_Leasing">
          <img
            src="../assets/image/popular_Leasing.png"
            alt=""
            class="popular_Leasing_img"
          />
          <div class="popular_Leasing_content">
            <div class="popular_Leasing_content_layout">
              <div
                class="popular_Leasing_card"
                v-for="({ image, name, daily, money, id }, index) of hot_phone"
                :key="index"
                @click="jumpPage(id)"
              >
                <img
                  src="../assets/image/product_bg.png"
                  alt=""
                  class="product_bg"
                />
                <img :src="image" alt="" class="hot_lease_phone" />
                <div class="goods_name">
                  <div class="new">全新</div>
                  <div class="product">{{ name }}</div>
                </div>
                <div class="daily_price">日常价:￥{{ daily }}/天</div>
                <div class="hot_lease_btn">
                  <div class="hot_lease_btn_layout">
                    <div class="rmb">￥</div>
                    <div class="price">{{ money }}</div>
                    <span class="day">/天</span>
                  </div>
                  <div class="line"></div>
                  <div class="lease_title">租</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="zone">
        <img
          src="../assets/image/exclusive_zone.png"
          mode=""
          class="exclusive_zone"
        />
        <div class="zone_content">
          <div class="zone_header">
            <img
              src="../assets/image/zone/more_phone.png"
              class="more_money"
              alt=""
            />
          </div>
          <div class="zone_product">
            <div class="zone_product_header">
              <div
                class="header_product"
                :style="!index && 'margin-right: 4px'"
                v-for="(
                  { image, name, tag, daily, vertical_reduction, money, id },
                  index
                ) of zone_header_phone"
                :key="id"
                @click="jumpPage(id)"
              >
                <img :src="image" alt="" class="zone_header_img" />
                <div class="header_product_content">
                  <div class="name">
                    <div class="tag">{{ tag }}</div>
                    <div class="product_name">{{ name }}</div>
                  </div>
                  <div class="daily">日常价:￥{{ daily }}/天</div>
                  <div class="vertical_reduction">
                    立减
                    <div class="price">{{ vertical_reduction }}</div>
                    元
                  </div>
                  <div class="zone_header_btn">
                    <img
                      src="../assets/image/zone/zone_btn.png"
                      alt=""
                      class="zone_header_btn_img"
                    />
                    <div class="zone_header_btn_content">
                      <div class="price">
                        <span style="margin-right: 2px">￥</span>
                        <span class="money">{{ money }}</span
                        >/天
                      </div>
                      <div class="rent">租</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="vertical_reduction_zone">
              <div
                class="product_layout"
                v-for="(
                  { image, name, tag, daily, money, id }, index
                ) of zone_content_phone"
                :key="index"
                :style="++index % 3 === 0 ? 'margin-right: 0;' : ''"
                @click="jumpPage(id)"
              >
                <img :src="image" class="zone_content_phone_img" />
                <div class="zone_content_phone_header">
                  <div class="tag">{{ tag }}</div>
                  <div class="product">{{ name }}</div>
                </div>
                <div class="daily">日常价:￥{{ daily }}/天</div>
                <div class="zone_content_btn">
                  <img
                    src="../assets/image/zone/zone_btn.png"
                    alt=""
                    class="zone_content_btn_img"
                  />
                  <div class="zone_btn_content">
                    <div class="price">
                      <span style="margin-right: 2px">￥</span>
                      <span class="money">{{ money }}</span
                      >/天
                    </div>
                    <div class="rent">租</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <img src="../assets/image/sets_img.png" alt="" class="sets_img" />
      <div class="sets_layout">
        <div
          class="sets_card"
          v-for="({ image, name, tag, daily, money, id }, index) of sets_phone"
          :key="index"
          :style="++index % 3 === 0 ? 'margin-right: 0;' : ''"
          @click="jumpPage(id)"
        >
          <img :src="image" alt="" class="sets_phone" />
          <div class="sets_content">
            <div class="tag">{{ tag }}</div>
            <div class="product">{{ name }}</div>
          </div>
          <div class="daily">日常价:￥{{ daily }}/天</div>
          <div class="set_content_layout">
            <img
              src="../assets/image/zone/zone_btn.png"
              alt=""
              class="sets_content_btn_img"
            />
            <div class="sets_btn_content">
              <div class="price">
                <span style="margin-right: 2px">￥</span>
                <span class="money">{{ money }}</span
                >/天
              </div>
              <div class="rent">租</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "saveMoney",
  data: () => ({
    hot_phone: [
      {
        image: require("../assets/image/hot_lease/hot_lease_phone1.png"),
        name: "苹果14ProMax",
        daily: "29.71",
        money: "28.40",
        id: "100661",
      },
      {
        image: require("../assets/image/hot_lease/hot_lease_phone2.png"),
        name: "苹果14 Pro",
        daily: "26.81",
        money: "25.50",
        id: "100663",
      },
      {
        image: require("../assets/image/hot_lease/hot_lease_phone3.png"),
        name: "苹果14 Plus",
        daily: "23.83",
        money: "22.52",
        id: "100664",
      },
    ],
    zone_header_phone: [
      {
        image: require("../assets/image/zone/zone_header_phone1.png"),
        name: "苹果14",
        tag: "全新",
        daily: "20.65",
        vertical_reduction: "400",
        money: "19.56",
        id: "100666",
      },
      {
        image: require("../assets/image/zone/zone_header_phone2.png"),
        name: "苹果14ProMax",
        tag: "99新",
        daily: "28.40",
        vertical_reduction: "400",
        money: "27.09",
        id: "100674",
      },
    ],
    zone_content_phone: [
      {
        image: require("../assets/image/zone/zone_content_phone1.png"),
        name: "苹果14 Pro",
        tag: "99新",
        daily: "25.02",
        money: "23.71",
        id: "100663",
      },
      {
        image: require("../assets/image/zone/zone_content_phone2.png"),
        name: "苹果14 Plus",
        tag: "99新",
        daily: "20.26",
        money: "19.16",
        id: "100664",
      },
      {
        image: require("../assets/image/zone/zone_content_phone3.png"),
        name: "苹果14",
        tag: "99新",
        daily: "18.27",
        money: "17.18",
        id: "100666",
      },
      {
        image: require("../assets/image/zone/zone_content_phone4.png"),
        name: "苹果13 Pro Max",
        tag: "全新",
        daily: "29.00",
        money: "27.68",
        id: "100674",
      },
      {
        image: require("../assets/image/zone/zone_content_phone5.png"),
        name: "苹果13 Pro",
        tag: "全新",
        daily: "26.61",
        money: "25.30",
        id: "100672",
      },
      {
        image: require("../assets/image/zone/zone_content_phone6.png"),
        name: "苹果13",
        tag: "全新",
        daily: "18.47",
        money: "17.38",
        id: "100671",
      },
      {
        image: require("../assets/image/zone/zone_content_phone7.png"),
        name: "苹果13 Pro Max",
        tag: "99新",
        daily: "24.23",
        money: "22.92",
        id: "100674",
      },
      {
        image: require("../assets/image/zone/zone_content_phone8.png"),
        name: "苹果13 Pro",
        tag: "99新",
        daily: "22.44",
        money: "21.13",
        id: "100672",
      },
      {
        image: require("../assets/image/zone/zone_content_phone9.png"),
        name: "苹果13",
        tag: "99新",
        daily: "16.09",
        money: "15.10",
        id: "100671",
      },
    ],
    sets_phone: [
      {
        image: require("../assets/image/sets/phone1.png"),
        name: "苹果12 Pro Max",
        tag: "95新",
        daily: "17.67",
        money: "16.58",
        id: "100681",
      },
      {
        image: require("../assets/image/sets/phone2.png"),
        name: "苹果12 Pro",
        tag: "95新",
        daily: "15.29",
        money: "14.31",
        id: "100682",
      },
      {
        image: require("../assets/image/sets/phone3.png"),
        name: "苹果12",
        tag: "95新",
        daily: "11.52",
        money: "10.70",
        id: "100683",
      },
      {
        image: require("../assets/image/sets/phone4.png"),
        name: "苹果11 Pro Max",
        tag: "95新",
        daily: "11.12",
        money: "10.30",
        id: "100678",
      },
      {
        image: require("../assets/image/sets/phone5.png"),
        name: "苹果11 Pro",
        tag: "95新",
        daily: "9.73",
        money: "8.91",
        id: "100679",
      },
      {
        image: require("../assets/image/sets/phone6.png"),
        name: "苹果11",
        tag: "95新",
        daily: "7.94",
        money: "7.29",
        id: "100680",
      },
    ],
  }),
  methods: {
    jumpPage(id) {
      window.location.href = `alipays://platformapi/startapp?appId=2021002129611863&page=page/rent/goodsdetail/goodsdetail?id=${id}`;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header_img {
  width: 100%;
  height: 300px;
}
.layout {
  padding: 0 9px;
  display: flex;
  flex-direction: column;
  background: #ff3333;

  .popular_Leasing_layout {
    width: 100%;
    height: 255px;
    .popular_Leasing {
      position: relative;
      width: 100%;
      height: inherit;
      &_img {
        position: absolute;
        width: 100%;
        height: inherit;
        height: 255px;
        top: 0;
      }
      &_content {
        position: absolute;
        z-index: 1;
        top: 60px;
        width: 100%;
        &_layout {
          display: flex;
          flex-direction: row;
          width: 100%;
          display: grid;
          display: flex;
          justify-content: space-evenly;
          .popular_Leasing_card {
            border-radius: 10px;
            background: #fff;
            width: 108px;
            height: 100%;
            padding: 5px 5px 7.5px 5px;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            .product_bg {
              width: 100%;
              height: 94.5px;
            }
            .hot_lease_phone {
              position: absolute;
              z-index: 1;
              width: 89.5px;
              height: 79.5px;
              top: 0;
              margin-top: 15px;
            }
            .goods_name {
              display: flex;
              justify-content: center;
              align-items: center;
              font-family: PingFang SC-Heavy, PingFang SC;
              color: #000000;
              margin-top: 8.5px;
              .new {
                border-radius: 4px;
                color: #fff;
                text-align: center;
                font-size: 8px;
                padding: 1px 4px;
                -webkit-transform: scale(0.9);
                white-space: nowrap;
                background: linear-gradient(180deg, #fc4c35 0%, #ff0000 100%);
              }
              .product {
                font-size: 12px;
                font-family: PingFang SC-Heavy, PingFang SC;
                font-weight: bold;
                color: #000000;
                white-space: nowrap;
              }
            }
            .daily_price {
              font-family: PingFang SC-Regular, PingFang SC;
              -webkit-transform: scale(0.8);
              font-size: 9px;
              font-weight: 400;
              color: #999999;
              margin-top: 4.5px;
              text-decoration: line-through;
            }
            .hot_lease_btn {
              width: 108.5px;
              margin-top: 6px;
              height: 24px;
              background: linear-gradient(90deg, #ff4373 0%, #ff6e32 100%);
              border-radius: 12px;
              color: #fff;
              display: flex;
              align-items: center;
              justify-content: center;
              cursor: pointer;
              &_layout {
                height: 20px;
                display: flex;
                align-items: flex-end;
                .rmb {
                  font-size: 9px;
                  -webkit-transform: scale(0.8);
                  font-family: PingFang SC-Bold, PingFang SC;
                  font-weight: bold;
                  color: #ffffff;
                  display: table-cell;
                  vertical-align: bottom;
                }
                .price {
                  font-size: 15px;
                  font-family: DINPro-Black, DINPro;
                  font-weight: 900;
                  color: #ffffff;
                  margin-bottom: 1px;
                }
                .day {
                  font-size: 8.5px;
                  -webkit-transform: scale(0.8);
                  font-family: PingFang SC-Bold, PingFang SC;
                  font-weight: bold;
                  color: #ffffff;
                }
              }
              .line {
                height: 10px;
                width: 1px;
                background: #fff;
                margin-left: 8.5px;
              }
              .lease_title {
                font-size: 14px;
                font-family: PingFang SC-Heavy, PingFang SC;
                font-weight: 800;
                color: #ffffff;
                margin-left: 5px;
              }
            }
          }
        }
      }
    }
  }
  .zone {
    position: relative;
    margin-top: 10px;
    .exclusive_zone {
      height: 695px;
      width: 100%;
      margin: 0 auto;
    }
    .zone_content {
      height: 695px;
      width: 100%;
      position: absolute;
      top: 0;
      display: grid;
      grid-template-rows: 8% 92%;
      .zone_header {
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        .more_money {
          width: 87px;
          height: 23px;
          margin-right: 7.5px;
        }
      }
      .zone_product {
        padding: 0 6px 6px 6px;
        // display: grid;
        // grid-template-rows: 100px 1fr;
        display: flex;
        flex-direction: column;
        .zone_product_header {
          display: flex;
          justify-content: space-around;
          .header_product {
            border-radius: 10px;
            background-color: #fff;
            width: 100%;
            display: flex;
            flex-direction: row;
            padding: 6px 2px 6px 6px;
            .zone_header_img {
              width: 55px;
              height: 80px;
            }
            .header_product_content {
              display: flex;
              flex-direction: column;
              width: 100%;
              .name {
                display: flex;
                justify-content: center;
                align-items: center;
                .tag {
                  border-radius: 4px;
                  color: #fff;
                  padding: 1px 4px;
                  font-size: 8px;
                  -webkit-transform: scale(0.9);
                  white-space: nowrap;
                  background: linear-gradient(180deg, #fc4c35 0%, #ff0000 100%);
                }
                .product_name {
                  font-size: 12px;
                  font-family: PingFang SC-Heavy, PingFang SC;
                  font-weight: bold;
                  color: #000000;
                  white-space: nowrap;
                }
              }
              .daily {
                font-size: 11px;
                -webkit-transform: scale(0.9);
                font-family: PingFang SC-Regular, PingFang SC;
                font-weight: 400;
                color: #999999;
                text-align: center;
                text-decoration: line-through;
              }
              .vertical_reduction {
                font-size: 9px;
                font-family: PingFang SC-Heavy, PingFang SC;
                font-weight: 800;
                -webkit-transform: scale(0.8);
                display: flex;
                justify-content: center;
                align-items: center;
                color: #e63428;
                .price {
                  font-size: 20px;
                  font-family: PingFang SC-Heavy, PingFang SC;
                  font-weight: 800;
                  color: #e63428;
                  margin-bottom: 2px;
                }
              }
              .zone_header_btn {
                height: 22.5px;
                position: relative;
                display: flex;
                justify-content: center;
                align-items: center;
                .zone_header_btn_img {
                  width: 100%;
                  height: inherit;
                }
                &_content {
                  width: 100%;
                  position: absolute;
                  display: flex;
                  justify-content: space-around;
                  align-items: center;
                  padding: 0 10px 0 0;
                  cursor: pointer;
                  .price {
                    font-size: 9px;
                    -webkit-transform: scale(0.8);
                    font-family: PingFang SC-Heavy, PingFang SC;
                    font-weight: 800;
                    color: #ffffff;
                    .money {
                      font-size: 15px;
                      font-weight: bold;
                      font-family: PingFang SC-Heavy, PingFang SC;
                    }
                  }
                  .rent {
                    font-size: 12px;
                    font-family: Alibaba PuHuiTi-Bold, Alibaba PuHuiTi;
                    font-weight: bold;
                    color: #ff101a;
                  }
                }
              }
            }
          }
        }
        .vertical_reduction_zone {
          display: flex;
          flex-flow: row wrap;
          .product_layout {
            height: 174px;
            width: 116px;
            background: #ffffff;
            border-radius: 10px;
            margin-top: 4.5px;
            margin-right: 4.5px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            .zone_content_phone_img {
              width: 89.5px;
              height: 85px;
            }
            .zone_content_phone_header {
              display: flex;
              justify-content: center;
              align-items: center;
              .tag {
                border-radius: 4px;
                color: #fff;
                text-align: center;
                font-size: 8px;
                padding: 1px 4px;
                -webkit-transform: scale(0.9);
                white-space: nowrap;
                background: linear-gradient(180deg, #fc4c35 0%, #ff0000 100%);
              }
              .product {
                font-size: 12px;
                font-family: PingFang SC-Heavy, PingFang SC;
                font-weight: bold;
                color: #000000;
                white-space: nowrap;
              }
            }
            .daily {
              font-family: PingFang SC-Regular, PingFang SC;
              -webkit-transform: scale(0.9);
              font-size: 11px;
              font-weight: 400;
              color: #999999;
              margin: 4.5px 0;
              text-decoration: line-through;
            }
            .zone_content_btn {
              height: 22.5px;
              position: relative;
              display: flex;
              justify-content: center;
              align-items: center;
              .zone_content_btn_img {
                width: 100%;
                height: inherit;
              }
              .zone_btn_content {
                width: 100%;
                position: absolute;
                display: flex;
                justify-content: space-around;
                align-items: center;
                padding: 0 10px 0 0;
                cursor: pointer;
                .price {
                  font-size: 9px;
                  -webkit-transform: scale(0.8);
                  font-family: PingFang SC-Heavy, PingFang SC;
                  font-weight: 800;
                  color: #ffffff;
                  .money {
                    font-size: 15px;
                    font-weight: bold;
                    font-family: PingFang SC-Heavy, PingFang SC;
                  }
                }
                .rent {
                  font-size: 12px;
                  font-family: Alibaba PuHuiTi-Bold, Alibaba PuHuiTi;
                  font-weight: bold;
                  color: #ff101a;
                }
              }
            }
          }
        }
      }
    }
  }
  .sets_img {
    height: 32.5px;
    width: 100%;
    margin: 9px 0;
  }
  .sets_layout {
    width: 362px;
    height: 368.5px;
    border-radius: 10px;
    background-color: #fff8db;
    margin-bottom: 16px;
    display: grid;
    display: flex;
    flex-flow: row wrap;
    padding: 7px 5px 0 5px;
    .sets_card {
      width: 117px;
      height: 174px;
      background-color: white;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-right: 4.5px;
      .sets_phone {
        width: 89.5px;
        height: 85px;
      }
      .sets_content {
        display: flex;
        justify-content: center;
        align-items: center;
        .tag {
          border-radius: 4px;
          color: #fff;
          text-align: center;
          font-size: 8px;
          padding: 1px 4px;
          -webkit-transform: scale(0.9);
          white-space: nowrap;
          background: linear-gradient(180deg, #fc4c35 0%, #ff0000 100%);
        }
        .product {
          font-size: 12px;
          font-family: PingFang SC-Heavy, PingFang SC;
          font-weight: bold;
          color: #000000;
          white-space: nowrap;
        }
      }
      .daily {
        font-family: PingFang SC-Regular, PingFang SC;
        -webkit-transform: scale(0.9);
        font-size: 11px;
        font-weight: 400;
        color: #999999;
        margin: 4.5px 0;
        text-decoration: line-through;
      }
      .set_content_layout {
        height: 22.5px;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        .sets_content_btn_img {
          width: 100%;
          height: inherit;
        }
        .sets_btn_content {
          width: 100%;
          position: absolute;
          display: flex;
          justify-content: space-around;
          align-items: center;
          padding: 0 10px 0 0;
          cursor: pointer;
          .price {
            font-size: 9px;
            -webkit-transform: scale(0.8);
            font-family: PingFang SC-Heavy, PingFang SC;
            font-weight: 800;
            color: #ffffff;
            .money {
              font-size: 15px;
              font-weight: bold;
              font-family: PingFang SC-Heavy, PingFang SC;
            }
          }
          .rent {
            font-size: 12px;
            font-family: Alibaba PuHuiTi-Bold, Alibaba PuHuiTi;
            font-weight: bold;
            color: #ff101a;
          }
        }
      }
    }
  }
}
</style>
