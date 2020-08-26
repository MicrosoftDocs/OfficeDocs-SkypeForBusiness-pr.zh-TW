---
title: '在通話品質儀表板中上傳租使用者並建立資料 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何在通話品質儀表板 (CQD) 中上傳租使用者和組建資料。
ms.openlocfilehash: 37499cf2715a3cabb05ab5039a19190190253b07
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897833"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>在通話品質儀表板中上傳租使用者並建立資料 (CQD) 


若要充分利用通話品質儀表板 (CQD) ，建議您上傳租使用者並建立資料。 有2種類型的租使用者資料檔，即 [建立](#upload-building-data-file) 與 [端點](#endpoint-data-file)。

您可以 [在這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例租使用者資料範本。 如需有關建立對應的說明，請參閱 [建立 CQD 的組建地圖](CQD-building-mapping.md)。

從 [CQD 摘要報告] 儀表板中，從 [CQD**設定**] 功能表中選取 **[租使用者資料上傳**]， (位於 [CQD]) 頂端的齒輪圖示。 在此，系統管理員可以上傳其組織的建築物和端點資訊，例如 IP 位址和地理資訊的對應、對應每個無線存取點及其 MAC 位址等。

1. 從 [團隊系統管理中心] 開啟 [CQD (]，或在 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) ，選取右上角的齒輪圖示，然後從 [**摘要報告**] 頁面選擇 [**租使用者資料上傳**]。

   ![上傳資料時出現之對話方塊的螢幕擷取畫面](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果這是您第一次造訪 CQD，系統會要求您上傳 [組建資料]。 您可以選取 **[立即上傳** ]，快速流覽至 [ **租使用者資料上傳** ] 頁面。

   ![通知使用者上傳建立資料的橫幅螢幕擷取畫面](media/qerguide-image-buildingdatauploadbanner.png)

3. 在 [ **租使用者資料上傳** ] 頁面上，選取 **[流覽]** 來選擇資料檔案。

4. 選取資料檔之後，請指定 **開始日期** ，也可以指定結束日期。

5. 選取 [ **開始日期**] 後，選取 **[上傳** ]，將檔案上傳到 CQD。 <br><br>檔案上傳之前，會進行驗證。 如果驗證失敗，則會顯示一則錯誤訊息，要求您更正檔案。 下圖顯示當資料檔案中的欄數不正確時所發生的錯誤。

   ![顯示組建資料上傳錯誤的對話方塊範例](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果驗證期間沒有發生任何錯誤，檔案上傳就會成功。 接著，您可以在 [我的上 **傳** ] 資料表中看到上傳的資料檔，該檔案會在該頁面的底部顯示目前租使用者的所有已上傳檔案的完整清單。

> [!NOTE]
> 可能需要長達四個小時的時間，才能完成建立檔的處理。 <br><br> 如果您已上傳檔案，且需要新增可能已錯過或排除的子網，請修改原始檔案，方法是新增子網、移除目前的檔案，然後重新上傳新編輯的檔案。 在 CQD 中，只能有一個作用中的組建資料檔案。 


## <a name="upload-building-data-file"></a>上傳資料檔案

CQD 中的第一個租使用者資料檔類型就是 **組建** 資料檔案。 [子網] 欄是透過展開 [網路 + NetworkRange] 欄，然後將 [子網] 欄加入通話記錄的第一個子網或 [第二個子網] 欄，來顯示建築物、城市、國家或地區資訊。 您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：
  
- 檔案必須是 tsv 檔案， (資料行是由索引標籤分隔，) 或 .csv 檔案 (欄之間以) 逗號分隔。

- 資料檔案不包含表格標題列。 資料檔案的第一行應該是真實資料，而不是標頭標籤（例如「網路」）。

- 檔案中的資料類型只能是 String、Integer 或 Boolean。 針對整數資料類型，此值必須是一個數值。 布林值必須是0或1。

- 如果資料行使用 [字串] 資料類型，資料欄位可以是空的，但仍必須以 tab 或逗號分隔。 空白資料欄位只會指派空的字串值。

- 每個資料列必須有14個數據行，每一欄都必須具有適當的資料類型，且欄必須按照下表所列的順序 (逗號或定位字元分隔) ：

  **建立資料檔案格式**
  
  | 欄名稱        | 資料類型 | 範例                   | 指導方針              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | 必要              |
  | NetworkName        | String    | 美國/西雅圖/西雅圖-海-1 | 必要<sup>1</sup>  |
  | NetworkRange       | 電話    | 26                        | 必要              |
  | BuildingName       | String    | 北京-海-1             | 必要<sup>1</sup>  |
  | OwnershipType      | String    | 尚未                   | 選用              |
  | BuildingType       | String    | 終止            | 選用              |
  | BuildingOfficeType | String    | 工程學               | 選用              |
  | 座               | String    | 西雅圖                   | 採用           |
  | 郵遞區號            | String    | 98001                     | 採用           |
  | 國家            | String    | 一下                        | 採用           |
  | 市              | String    | 華盛頓                        | 採用           |
  | 地區             | String    | MSUS                      | 採用           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | 必要              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | 必要              |
  | 點對點                | Bool      | 0                         | 選用              |

  <sup>1</sup> 當 CQD 不需要時，範本會設定為顯示建築物和網路名稱。

  <sup>2</sup> 這個設定可以用來反映子網上是否位於公司網路內。 您可以自訂用法以用於其他用途。

  <sup>3</sup> 這個設定可用來反映網路使用的是 Azure ExpressRoute。 您可以自訂用法以用於其他用途。  

  **範例列：**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 網路範圍可以用來代表幾個子網的 (supernet 組合，) 的單一路由前置詞。 所有新的建築物上傳都會被檢查，以取得任何重迭的範圍。 如果您先前上傳的是組建檔案，您應該下載目前的檔案，然後重新上傳以找出任何重疊，並修正問題，然後再重新上傳。 先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。 某些 VPN 實現不會精確地報告子網資訊。 
>
> [VPN] 欄是選擇性的，預設為0。 如果 VPN 欄的值設為1，則該資料列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。  請謹慎使用這個方式，然後只針對 VPN 子網，因為完全擴充這些子網會對涉及建立資料之查詢的查詢時間造成負面影響。


### <a name="supernetting"></a>Supernetting

您可以使用 supernetting （通常稱為無類別的網域間路由 (CIDR），) 代替定義每個子網。 *Supernet*是多個子網的組合，可共用單一路由前置詞。 您可以使用 supernetted 位址，而不是為每個子網新增專案。 支援 Supernetting，但我們不建議使用它。

例如，Contoso 的行銷大樓是由下列子網組成：

-   10.1.0.0/24-第一層
-   10.1.1.0/24-第二層
-   10.1.2.0/24-第三層
-   10.1.3.0/24-第四層

您可以使用 supernetted 位址（在此範例中為 10.1.0.0/22），而不是為每個子網上新增專案。

-   Network = 10.1.0。0
-   網路範圍 = 22

在執行 supernetting 之前，請先考慮以下幾點：

-   Supernetting 只能在含有8位到28位元遮罩的子網對應中使用。

-   Supernetting 佔用較少的時間，但代價是減少資料的豐富程度。 假設有一個涉及子網10.1.2.0 的品質問題。 如果您已執行 supernetting，就不會知道組建子網上的位置，或是它所 (的網路類型（例如，實驗室) ）。 如果您已定義所有子網，以取得建築物和上傳的樓層位置資訊，您就可以看到這種差異。

-   務必確保 supernetted 位址正確無誤，而且不會捕捉不想要的子網。

-   在資料中找到192.168.0.0 是很常見的。 對於許多組織而言，這表示使用者是在家中。 對其他人而言，這是衛星辦公室的 IP 位址配置。 如果您的組織有使用這項設定的辦事處，請不要將它納入您的組建檔案中，因為很難使用 [通用子網](quality-of-experience-review-guide.md#common-subnets)來區分家用和內部網路。 

> [!IMPORTANT]
> 網路範圍可以用來代表 supernet。 所有新的組建資料檔案上傳都將會檢查任何重迭的範圍。 如果您先前上傳的是組建檔案，您應該下載目前的檔案並再次上傳，以找出任何重迭並修正問題。 先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。

### <a name="vpn"></a>點對點

當用戶端傳送至 Microsoft 365 或 Office 365 的 QoE) 資料（包括 VPN 標誌）時， (的體驗品質。 CQD 將會看到此為第一個 VPN 和第二個 VPN 維度。 不過，此標記會依賴 VPN 廠商的報告來向 Windows 確認 VPN 網路介面卡已註冊為遠端存取配接器。 並非所有的 VPN 供應商都正確註冊遠端存取配接器。 因此，您可能無法使用內建的 VPN 查詢篩選。 使用上述所述的 VPN 欄來精確標示及識別 VPN 子網。 為您的 VPN 網路加上標籤，以便在報表中輕鬆識別。 以下是兩個如何標示 VPN 子網的範例：

- 在這個 [VPN 子網] 欄位中輸入「VPN」，以定義 **網路名稱** 。

  ![使用網路名稱顯示 VPN 的 QCD 報告螢幕擷取畫面](media/qerguide-image-vpnnetworkname.png)

- 在這個 [VPN 子網] 欄位中輸入「VPN」來定義 **建築物名稱** 。

  ![使用建築物名稱顯示 VPN 的 QCD 報告螢幕擷取畫面](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> 當基礎連線是無線時，已知 VPN 連線是將網路連線類型 misidentify 為有線。 當您以 VPN 連線查看品質時，您無法假設正確識別了連線類型。

## <a name="endpoint-data-file"></a>端點資料檔案

另一種類型的 CQD 租使用者資料檔案是 **端點** 資料檔。 欄值會用於通話記錄的第一個用戶端端點名稱或第二個用戶端端點名稱欄，以顯示端點、模型或類型資訊。 您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：

- 檔案必須是 tsv 檔案， (資料行是由索引標籤分隔，) 或 .csv 檔案 (欄之間以) 逗號分隔。

- 資料檔案的內容不會包含表格標題。 資料檔案的第一行應該是真實資料，而不是像是 "終結點" 這樣的標頭標籤。

- 所有六個數據列都只使用 String 資料類型。 允許的最大長度為64個字元。

- 資料欄位可以是空的，但仍須以 tab 或逗號分隔。 空白資料欄位只會指派空的字串值。

- 終結點必須是唯一的，否則上傳就會失敗。 如果有重複的資料列，或是兩列使用相同的終結點，衝突將會導致不正確的聯接。

- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。 它們可以是空白字串或 "IT 部門指派2018膝上型電腦" 或 "資產標記 5678" 等值。

- 每個資料列必須有六個數據行，且欄必須以下列順序排列：

  **欄位順序：**

  終結點、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **範例列：**

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  


## <a name="update-a-building-file"></a>更新組建檔案

在收集建立和子網資訊時，系統管理員會經常在一段時間內，在多個反覆運算中上傳檔案，並在新的子網變為可用時，新增其建築物資訊。 發生這種情況時，您必須重新上傳您的組建檔案。 此程式就像上一節所述的初始上傳一樣，還有一些例外狀況，如下一節所述。

> [!Important]
> 一次只能有一個建立檔。 多個建築物檔案不是累加的。

## <a name="add-net-new-subnets"></a>新增全新子網

在某些情況下，您需要將全新的子網新增至 CQD，而不是原本是您的網路拓朴的一部分。 若要新增 net 新建子網，請在 CQD 中的 **租使用者資料上傳** 頁面執行下列動作：

1.  如果您還沒有最新的複本，請下載原始檔案。

1.  在 CQD 中移除目前的檔案。

1.  編輯原始的組建檔案，並提供至少在取得網路新子網前一天的結束日期。

1.  將全新的子網附加至原始的組建檔案。

1.  上傳新修改的組建檔案，並在前一個建築物檔案結束後的一天中設定開始日期。

## <a name="add-missing-subnets"></a>新增遺失的子網

在您上傳受管理的網路的建築物資訊之後，每個受管理的網路都應該有一個建築物關聯。 不過，這不一定是案例;通常會錯過幾個子網。 若要找出這些缺少的網路，請在 CQD 中查看 [**經驗品質報告**] 頁面上的 [**遺失的子網報告**]。 這會顯示有10個以上的音訊資料流程的所有子網，且未在建築物資料檔中定義，且標示為外部。 確定此清單中沒有受管理的網路。 如果子網遺失，請使用下列程式來更新原始的組建資料檔，並將它重新上傳到 CQD。

1. 移至 CQD 中的 **租使用者資料上傳** 頁面。

1. 如果您還沒有最新的複本，請下載原始檔案。

1. 在 CQD 中移除目前的檔案。

1. 將新的子網附加至原始檔案。

1. 上傳組建檔案。 請務必先將開始日期設為至少八個月，以便 CQD 會處理歷史資料。


> [!IMPORTANT]
> 您必須將您的租使用者識別碼，作為 **第二個租使用者識別碼** 的查詢篩選器新增至此報告，以篩選報表，以便只查看貴組織的租使用者資料。 否則，報表就會顯示聯盟子網。

> [!NOTE] 
> 請務必將 [月年度] 報表篩選調整為 [本月]。 選取 [ **編輯**]，然後調整 [ **月** ] 報表篩選，以儲存新的預設月份。


## <a name="related-topics"></a>相關主題

[建立 CQD 的建立地圖](CQD-building-mapping.md)

[改善及監視團隊的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話與會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md)
