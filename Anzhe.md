---
timezone: Asia/Shanghai
---

---

# Anzhe

1. 自我介绍
大家好，我是 Anzhe，是圖書資訊、資訊工程雙主修的大五學生，對資安領域感興趣，目前一邊補基礎一邊探索資訊、資安各種領域，希望能多多學習各種知識和技術，增加自身能力。
2. 你认为你会完成本次残酷学习吗？
我覺得這次殘酷共學對我來說是了解 Web3、區塊鍊和智能合約的好機會，同時也是對自我的挑戰，我會盡力規劃好時間，努力完成本次的共學目標。
## Notes

<!-- Content_START -->

### 2024.09.23
# Solidty
　　Solidity 是為了全球市值第二的加密貨幣市場乙太坊（Ethereum）創建的程式語言，發布於 2015 年，是為了實現智能合約而設計的物件導向高階程式語言、一種針對以乙太坊虛擬機器的花括號語言，它受到 C++、Python 和 JavaScript 的啟發，用來編寫可以自動執行合約條款的智能合約，更是區塊鍊運行平台的主要使用語言，可以用於創建投票、盲拍、群眾募資、多重簽名錢包等用途的合約。

### Solidity 主要特點
1. 靜態類型語言：編譯時需要指定每個變數的類型。
2. 合約繼承：支持合約的繼承，讓開發者可以重用程式碼。
3. 函數修飾器：用來修改函數的行為，例如限制只有合約擁有者可以調用某個函數。
4. 事件：智能合約可以發送事件，供前端應用或其他合約監聽。
# 智能合約
智能合約是乙太坊最大的創新之一，開發者編寫、部署自動執行合約條款的智能合約到乙太坊區塊鍊上，智能合約在部署到區塊鏈後，能夠不依賴第三方自動執行和記錄交易，並且記錄是不可更改的。
# 乙太坊
乙太坊是一個去中心化的開源區塊鍊平台，主要支援分散式（去中心化）應用和智能合約。和主要用於數字貨幣交易的比特幣和其他區塊鍊平台的差異在於：乙太坊提供了一個能夠執行編程邏輯的區塊鏈環境——乙太坊虛擬機(Ethereum Virtual Machine)，它是一個分散式的計算機網絡，保證每個節點能夠正確執行合約，開發者可以在其上構建和運行去中心化的應用。

---
# Solidity 101
開發工具 `Remix` : [https://remix.ethereum.org](https://remix.ethereum.org)
教程使用 `Remix` 運行 Solidity 合約，`Remix` 是乙太坊推薦基於瀏覽器的智能合約整合式開發環境（IDE）。

## Remix 開發流程
Remix 左側面板，選擇`文件`面板可以新增`檔名.sol`檔案用 Solidity 開始編寫只能合約，快捷鍵 `Ctrl + S` 可以對檔案進行編譯，選擇`部署`面板並點擊 `Deploy` 則可以把智能合約部署到區塊鍊上，`Remix`會分配一些測試帳號給使用者，每個帳號有 100 ETH 的測試幣可以使用，每次部署合約會扣掉一點點。
![](https://i.imgur.com/eBMY37U.png)

## Hello Web3 程式碼
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.21;
contract HelloWeb3{
    string public _string = "Hello Web3!";
}
```
### 說明
1. `//` 是單行註解，說明程式碼使用的 License 許可是 `MIT`，註解的內容不會被執行，若不寫許可程式仍可執行，只是編譯時可能會出現警告。
2. Soldity 語句需以 `;` 結尾。
3. `pragma solidity ^0.8.21;` 宣告文件使用的 Solidity 版本，版本不同會有語法差異，`^` 代表向後兼容，表示允許 0.8.21 版本以上的 0.8.x 版本編譯器編譯，但不包括 0.9.x 或更新的版本。
4. `contract HelloWeb3` 是創建合約，並宣告合約的名稱為 `HelloWeb3`，花括弧內則是合約的內容，宣告了一個字串的變數 `_string` 並賦值為 `Hello Web3!`。

部署完畢後，`部署`面板滑到最下方，可以看到名為 `HelloWeb3` 的智能合約，點擊變數 `_string` 可以看到變數儲存的內容。
![](https://i.imgur.com/JE6E9KQ.png)

### 2024.09.24
# Solidity 的變數類型
1. 數值類型（Value Type）
2. 函數類型（Function Type）
3. 引用類型（Reference Type）
4. 映射類型（Mapping Type）
---
# 數值類型
數值類型賦值時可直接傳遞數值，且數值類型的變數是互相獨立的。
分成以下類型：
1. 布林類型：`bool`。
2. 整數類型：`int`、`uint`。
3. 地址類型：`address`、`address payable`。
4. 固定長度位元組陣列：`bytes1`、`bytes32`。
5. 枚舉類型：`enum`。
## 1. 布林類型
`bool` 的值只有 `true` 和 `false` 兩種。
```
bool public _bool = true;
```
### 布林值的運算符：
* `!` NOT，非
* `&&` AND，與
* `||` OR，或
* `==` 等於
* `!=` 不等於
```
bool public _bool1 = !_bool; // 取 NOT，_bool1 結果是 false
bool public _bool2 = _bool && _bool1; // AND，_bool2 結果是 false
bool public _bool3 = _bool || _bool1; // OR，_bool3 結果是 true
bool public _bool4 = _bool == _bool1; // 相等，_bool4 結果是 false
bool public _bool5 = _bool != _bool1; // 不相等，_bool5 結果是 true
```
### 短路規則
* 若存在 f(x) || g(y) 的表達式，如果 f(x) 是 true，結果一定是 true，第二個條件 g(y) 就不會被計算、判斷。
* 若存在 f(x) && g(y) 的表達式，如果 f(x) 是 false，結果一定是 false，第二個條件 g(y) 就不會被計算、判斷。
## 2. 整數類型
* `int` 是有號整數，從 `int8` 、`int16` ……到 `int256`，後面都是接 8 的倍數，表示占幾位元，`int8` 的範圍是 -128 ~ 127。`int256` 可直接由 `int` 表示。
* `uint` 是無號整數，從 `uint8` 到 `uint256`，後面都是接 8 的倍數，表示佔幾位元，`uint8` 的範圍是 0~ 255。`uint256` 可直接由 `uint` 表示。
### 整數運算符
| 比較運算符 | 算術運算符 |
|-----------|-----------|
|`<=` 小於等於 |`+` 加法 |
|`<` 小於 |`-` 減法|
|`==` 等於 |`*` 乘法|
|`!=` 不等於 |`/` 除法|
|`>=` 大於等於 |`%` 取餘數|
|`>` 大於 |`**` 冪次|

```
int public _int = -1; // 整數，包含負數
uint public _uint = 1; // 正整數
uint256 public _number = 20220330; // 256 位元正整數

uint256 public _number1 = _number + 1; // 四則運算，_number1 是 20220331
uint256 public _number2 = 2**2; // 指數，_number2 是 4
uint256 public _number3 = 7 % 2; // 取餘數，_number3 是 1
bool public _numberbool = _number2 > _number3; // 比大小，_number4 是 true
```
## 3. 地址類型
地址類型分成：
* `address`：儲存 20 byte 的乙太坊地址。
* `address payable` 類似 `address` 但比普通地址多了 `transfer` 和 `send` 的成員方法，用於轉帳乙太幣，不過 send 在轉帳失敗時只會回傳 false，而不會回復交易狀態，開發者需要自行處理失敗狀況。
```
address public _address = 0x7A58c0Be72BE218B41C608b7Fe7C5bB630736C71;
address payable public _address1 = payable(_address);
uint256 public balance = _address1.balance; 
_address1.transfer(1);
```
### 說明：
* `payable(_address)` 將普通的 address 轉換為 payable address，用來允許此地址之後可以轉帳、查餘額。
* `_address1.balance` 用來獲取地址持有的乙太幣餘額。
* `_address1.transfer(1);` 從合約的餘額中向 `_address1` 地址發送 `1 wei`（1 以太幣等於 10^18 wei）。transfer() 會在發送失敗時自動回退交易並拋出錯誤，因此它是一個安全進行資金轉移的方式。
## 4. 固定長度位元組陣列
位元組陣列分成固定長度和不固定長度兩種，固定長度的位元組陣列屬於數值類型，陣列長度在宣告之後不能改變，長度分為從 `bytes1`、`bytes8`、……，最多到 `bytes32`。
不定長度的位元組陣列屬於引用類型，在宣告後可以改變長度，包含 `bytes`，之後會提到。
```
bytes32 public _byte32 = "MiniSolidity";
bytes1 public _byte1 = _byte32[0];
bytes2 public _byte2 = _byte32[1];
```
### 說明：
`"MiniSolidity"` 以位元組的方式儲存進變數 _byte32，用 16 進制來看就是 `0x4d696e69536f6c69646974790000000000000000000000000000000000000000`，`_byte32[0]` 擷取第一個位元組 `0x4d` 的部分，存入變數 `_byte1` 中，`_byte32[1]` 擷取第二個位元組 `0x69` 的部分，存入變數 `_byte2` 中。

## 5. 枚舉類型
`enum` 是 Solidity 中由使用者定義的資料類型，主要用在位 `uint` 分配名稱，使程式易於閱讀和維護，他與 C 語言的 enum 類似，使用名稱來代替從 0 開始的 `uint`。
```
enum ActionSet { Buy, Hold, Sell }
ActionSet action = ActionSet.Buy;
function enumToUint() external view returns(uint){
    return uint(action);
}
```
說明：
* `enum ActionSet { Buy, Hold, Sell }` 用 enum 將 uint 0, 1, 2 表示為 Buy, Hold, Sell
* `ActionSet action = ActionSet.Buy;` 建立 enum 變數 action，並將 action 初始化為 ActionSet.Buy，action 變數當前的值對應 enum 中的 Buy，其數值是 0。
* `external` 是一個外部函數，可以被外部合約或外部使用者呼叫。
* `view` 表示這個函數不會改變合約的狀態，只是查看（讀取）資料。
* `returns(uint)` 指定函數的返回類型為 `uint`。
* `return unit(action)` 將 action 的值轉換為 uint，並返回這個值。由於 action 被設為 ActionSet.Buy，其對應的整數值是 0。
* enum 可以和 uint 進行顯式轉換，轉換的正整數需在枚舉長度內，否則會 Error。

### 2024.09.25
今天的內容主要是關於 Solidity 的函數，要注意的是函數概念有分成「函數類型的變數」和「函數」，不是所有函數都有函數類型的變數，但函數可以被賦值給函數類型的變數。
函數分成內部函數和外部函數，內部函數只能在當前合約中呼叫，包括內部函式庫和繼承函數，因為呼叫內部函數透過跳到入口標籤來內部呼叫當前合約的函數。
外部函數由位址和函數簽名組成，可以作為參數傳遞給其他函數，並且也可以從其他函數中返回。
# 函數的語法
```
function <function name>(<parameter types>) {internal|external|public|private} [pure|view|payable] [returns (<return types>)]
```
### 說明
* `function` 基本的函數宣告關鍵字。
* `<function name>` 函數名稱。
* `<parameter types>` 傳入到函數內部的參數，要替換成變數類型和變數名稱。
* `{internal|external|public|private}` 是可見性類型，必須指定一個。只有函數變數才預設是 `internal`。
    * `internal` 只能從合約內部訪問，繼承的合約可以用。
    * `external` 只能從合約外部存取（但內部可以透過 this.f() 來調用，f是函數名稱）。
    * `public` 合約內部和外部皆可見。
    * `private` 只能從本合約內部訪問，繼承的合約也不能使用。
    * 註：`public|private|internal` 也可用於修飾**狀態變數**。 `public` 變數會自動產生同名的`getter` 函數，用來查詢數值。未標示可見性類型的狀態變數，預設為`internal`。
* `[pure|view|payable]` 是返回值類型，非必要，決定函數權限、功能的關鍵字。合約的狀態變數儲存在鏈上，改寫鍊上狀態需支付氣費（gas fee），`pure` 和 `view` 不改寫鍊上狀態，所以調用此類函數不用支付氣費。
    * `pure` 函數既不能讀取也不能寫入鏈上的狀態變數。
    * `view` 函數能讀取但也不能寫入狀態變數。
    * `payable` 函數運行時可以給合約轉入乙太幣。
* `[returns ()]` 返回值類型和名稱，非必要。

乙太坊的修改鍊上狀態包括：
1. 寫入狀態變數。
2. 釋放事件。
3. 創建其他合約。
4. 使用 `selfdestruct`
5. 透過調用發送以太幣。
5. 呼叫任何未標記 view 或 pure 的函數。
6. 使用低階呼叫（low-level calls）。
7. 使用包含某些操作碼（Opcodes）的內聯彙編（Inline Assemply）。

---
# 程式碼
## 1. Pure 和 View
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.21;
contract FunctionTypes{
    uint public number = 0;  // 在合約中定義一個狀態變數 number，public 表示變數合約內部和外部皆可見，初始化為 0
    function add() external{
        number = number + 1;
    }
    function addPure(uint256 _number) external pure returns(uint256 new_number){
        new_number = _number + 1;
    }
    function addView() external view returns(uint256 new_number) {
        new_number = number + 1;
    }
}
```
### 說明
* 如果 `add()` 被標記為 `pure` 就會報錯，因為 `pure` 不配合讀取或改寫合約裡的狀態變數；如果 `add()` 函數被標記為 `view` 也會報錯，因為 view 能讀取，但無法改寫狀態變數。
* `addPure()` 傳遞參數 `_number` 並回傳 `_number + 1`，不會有讀取或寫入狀態變數的操作。
![](https://i.imgur.com/mIlAEyI.png)
可以看到當我按 23 次橘色（執行 23 次 add() 函數），number 的值就會增加到 23；而當我執行 `addPure()` 時，我必須輸入一個數字(34)才能執行，執行結果 new_number 是 35，和合約的狀態變量無關，如果不給輸入參數就無法調用 `addPure()`；而當我執行 `addView()` 時，我可以讀取合約的狀態變數 23，所以結果是合約的狀態變數 +1 變成 24。
## 2. internal 和 external
```
    // 接續前面繼續寫
    function minus() internal {
        number = number - 1;
    }
    function minusCall() external{
        minus();
    }
```
重新部署合約後，狀態值會重設，可以發現內部函數 `minus()` 無法調用所以沒有出現，只有新增 `minusCall()` 也是 `external` 可被外部調用，然後間接調用內部函數 `minus()`。
![](https://i.imgur.com/7Q07uxx.png)
## 3. payable
```
    // 接續前面繼續寫
    function minusPayable() external payable returns(uint balance){
        minus();
        balance = address(this).balance;
    }
```
`this` 關鍵字可以引用當前合約地址，然後用 `地址.balance` 返回合約的乙太幣餘額。
在 Deploy 上方可以輸入要轉入多少、選擇幣的單位，然後按 minusPayable() 就可以往合約裡轉入多少幣。
![](https://i.imgur.com/fupwihn.png) ![](https://i.imgur.com/2eQqNzM.png)
註：要注意 minus() 不能把 `number` 扣光，不然會交易失敗然後被 revert。
# 函數輸出
函數輸出的關鍵字 `returns` 在函數名稱後面宣告回傳的變數類型與變數名稱，`return`則是在函數定義中返回指定的變數：
```
function returnMultiple() public pure returns(uint256, bool, uint256[3] memory){
    return (1, true, [uint256(1), 2, 5]);
}
```
`returns` 宣告了 `returnMultiple()` 有多個返回值，對應 `return(1, true, [uint256(1),2,5])` 實際的返回值內容。第三個返回值宣告了長度為 3 且類型為 `uint256` 的數列，數列類型的返回值需用 `memory` 修飾。因為 `[1,2,5]` 的型別會默認為 `uint8(3)`，所以強轉第一個元素來宣告陣列元素皆為 `uint256`。
## 命名式回傳
若在 `returns` 中標示回傳變數的名稱，Solidity 會自動初始化這些變數，並自動回傳函數的值，不須使用 `return`。
```
function returnNamed() public pure returns(uint256 _number, bool _bool, uint256[3] memory _array){
    _number = 2;
    _bool = false;
    _array = [uint256(3),2,1];
}
```
命名式也可以用 `reutrn` 回傳變數：
```
function returnNamed2() public pure returns(uint256 _number, bool _bool, uint256[3] memory _array){
    return (1, true, [uint256(1), 2, 5]);
}
```
## 解構式賦值
Solidity 可以用解構式賦值規則來讀取函數的全部或部分回傳值。
1. 讀取所有返回值：宣告變數，然後依序將要賦值的變數以,隔開。
```
uint256 _number;
bool _bool;
uint256[3] memory _array;
(_number, _bool, _array) = returnNamed();
```
2. 讀取部分傳回值：宣告要讀取的回傳值對應的變數，不讀取的留空。
```
bool _bool2;
(, _bool2, ) = returnNamed(); // 只讀取_bool，而不讀取傳回的_number和_array
```
寫進 function 內再執行：
```
function ReadReturn() public pure{
    uint256 _number;
    bool _bool;
    uint256[3] memory _array;
    (_number, _bool, _array) = returnNamed();
    bool _bool2;
    (, _bool2, ) = returnNamed();
}
```
## 執行結果
![](https://i.imgur.com/Bhud5Up.png)
<!-- Content_END -->
