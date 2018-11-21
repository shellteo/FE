# 动态规划

```javascript
//x行y列矩阵图求路径条数问题（简单dp）
function main(x,y){
    var arr=[];
    for (var i = 0; i < x; i++) {
        arr[i] = [];
        for (var j = 0; j < y; j++) {
            arr[i][j]=0;
        }
    }
    for(var j=0;j<y;j++)
        arr[0][j]=1;              //第一行进行初始化
    for(var i=0;i<x;i++)
        arr[i][0]=1;              //第一列进行初始化
    console.log(arr);
    for(var i=1;i<x;i++)
    {
        for(var j=1;j<y;j++)
            arr[i][j]=arr[i][j-1]+arr[i-1][j];   //状态转移方程
    }
    return arr[x-1][y-1];
}
console.log(main(4,2));
```

找零问题

```javascript
/**
 * 找零问题变种
 * @param n
 * @returns {*}
 */
function solution(n){
    if(n<=0) return 0;
    var coins=[1,5,10,20,50,100];
    var dp=[];
    for (var k = 0; k < n+1; k++) {
        dp[k]=0;
    }
    dp[0]=1;
    for(var i=0;i<coins.length;i++)
    {
        for(var j=coins[i];j<=n;j++)
        {
            dp[j] =dp[j]+dp[j-coins[i]];
        }
        console.log(dp);
    }
    return dp[n];
}
console.log(solution(10));


/**
 * 找零问题：给定一组硬币数，找出一组最少的硬币数，来找换零钱N
 * 比如，可用来找零的硬币为: 1、3、4   待找的钱数为 6。用两个面值为3的硬币找零，最少硬币数为2。而不是 4，1，1
 * @param n
 * @returns {*}
 */
function s2(coins,n){
    if(n<=0)return 0;
    var temp=n;
    /*注意js自带的sort排序，要加一个回掉函数，不然排序出来很可能不是从小到大*/
    coins = coins.sort(function (a, b) {
        return a-b;
    });
    var arr=[];
    while(temp>0){
        for(var i=coins.length-1;i>=0;i--){
            if(coins[i]<=temp){
                temp=temp-coins[i];
                arr.push(coins[i]);
                break;
            }
        }
    }
    return arr;
}
console.log(s2([1,5,25],32));
//console.log([1, 5, 25].sort(function (a, b) {
//    return a-b;
//}));
//console.log(s2([1, 3, 4], 6));

/**
 * 动态规划实现找零问题
 * @param sum
 * @returns {*}
 */
function dp2(sum){
    var a= [1,3,5],dp=[]; 
    dp[0] = 0;
    for ( var i = 1; i <= sum; i++) dp[i] = i; //我们假设存在1元的硬币那么i元最多只需要i枚1元硬币，当然最好设置dp[i]等于无穷大
    for ( var i = 1; i <= sum; i++){
        for ( var j = 0; j < 3; j++){
            if (i >= a[j] && dp[i - a[j]] + 1 < dp[i]){
                dp[i] = dp[i- a[j] ] + 1;
            }
        }
        console.log(dp);
    }
    return dp[sum];
}
console.log(dp2(11));

function MyDp (target){
    var arr=[2,3,4,10,11];
    var dp=[];
    dp[0]=0;
    for(var m=1;m<=target;m++){
        dp[m]=Infinity;
    }
    for(var i=1;i<=target;i++){
        for(var j=0;j<arr.length;j++){
            if(arr[j>i])break;
            if(arr[j]<=i&&dp[i-arr[j]]+1<dp[i]){
                dp[i]=dp[i-arr[j]]+1;
            }
        }
    }
    return dp[target];
}
console.log(MyDp(20));
```