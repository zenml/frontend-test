<template>
    <li class="trans-item">
        <div class="left-wrap">
            <img :src="carTypeImage" :alt="typeName" />
            <div>{{ carLong + "米 " + loadingType }}</div>
        </div>
        <div class="mid-wrap">
            <div class="line-left">
                <div class="start-address">
                    {{ startAddress.city.name + startAddress.district.name }}
                </div>
                <div>
                    载货体积：{{ `${carLong}*${carWidth}*${carHeight}` }}m
                </div>
            </div>
            <div class="line-mid">
                <div>{{ hoursLength }}h</div>
                <div>--></div>
                <div>{{ distance }}km</div>
            </div>
            <div class="line-right">
                <div class="end-address">
                    {{ endAddress.city.name + endAddress.district.name }}
                </div>
                <div>载货重量：{{ carload }}吨</div>
            </div>
        </div>
        <div class="right-wrap">
            <div class="price-wrap">
                <div class="price">一口价：￥{{ price }}</div>
                <div>累计已发：{{ usageCount }}车</div>
            </div>
            <button>立即用车</button>
        </div>
    </li>
</template>

<script>
export default {
    name: "TransItem",
    props: {
        /** 车名*/
        typeName: String,
        /** 载重*/
        carload: Number,
        /** 车长*/
        carLong: Number,
        /** 车宽*/
        carWidth: Number,
        /** 车高*/
        carHeight: Number,
        /** 始发地*/
        startAddress: Object,
        /** 目的地*/
        endAddress: Object,
        /** 线路耗时*/
        hoursLength: Number,
        /** 线路距离*/
        distance: Number,
        /** 价格*/
        price: Number,
        /** 车辆图片链接*/
        carTypeImage: String,
        /** 使用次数*/
        usageCount: Number,
        /** 栏杆类型*/
        loadingType: String
    }
};
</script>

<style scoped lang="less">
.trans-item {
    height: 178px;
    list-style: none;
    display: flex;
    align-items: center;
    & > div {
        flex-grow: 1;
    }
    .left-wrap {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        img {
            border: 1px solid #ccc;
            width: 170px;
            height: 108px;
            border-radius: 10px;
            border-width: 2px;
        }
    }
    .mid-wrap {
        display: flex;
        align-items: center;
        & > * {
            flex-grow: 1;
        }
        .line-left {
            .start-address {
                font-weight: bold;
                font-size: 20px;
            }
        }
        .line-right {
            .end-address {
                font-size: 20px;
                font-weight: bold;
            }
        }
    }
    .right-wrap {
        display: flex;
        & > * {
            flex-grow: 1;
        }
        .price {
            font-size: 22px;
            font-weight: bold;
            color: #fa8802;
        }
        button {
            background-color: #fa8802;
            border: 0;
            outline: 0;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
    }
}
</style>
