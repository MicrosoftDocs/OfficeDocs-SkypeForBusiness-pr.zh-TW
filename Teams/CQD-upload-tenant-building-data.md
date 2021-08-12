---
title: 'Upload通話品質儀表板中建立租使用者和 (CQD) '
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
description: 瞭解如何在 CQD (中上傳租使用者和) 。
ms.openlocfilehash: be51f4ec7eb19f56a07413749abf5455856754ed0984d00cd27ed72d9aaa8316
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322805"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Upload通話品質儀表板中建立租使用者和 (CQD) 


若要在 CQD (中) 通話品質儀表板，建議您上傳租使用者和建築物資料。 有 2 種類型的租使用者資料檔案，[即建築物和](#upload-building-data-file)[端點](#endpoint-data-file)。

您可以在這裡下載範例租使用者資料 [範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。 若要瞭解建立地圖的協助，請參閱建立 [CQD 的建築物地圖](CQD-building-mapping.md)。

在 CQD 摘要報表儀表板中，選取 CQD Upload 功能表中的設定 租使用者資料 (CQD 功能表頂端的齒輪圖示) 。 管理員可以從這裡上傳其組織的建築物和端點資訊，例如 IP 位址和地理資訊的映射、每個無線存取點及其 MAC 位址的映射等。

1. 從 (Teams 系統管理中心或) 開啟 CQD) ，然後選取右上角的齒輪圖示，然後從摘要報表頁面選擇 Upload 租使用者資料。 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)  

   ![上傳資料時出現的對話方塊螢幕擷取畫面](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果這是您第一次流覽 CQD，系統將會要求您上傳建築物資料。 您可以選取 Upload **立即** 流覽至租使用者 **資料Upload** 頁面。

   ![通知使用者上傳建築物資料的橫幅螢幕擷取畫面](media/qerguide-image-buildingdatauploadbanner.png)

3. 在租 **使用者資料Upload** 頁面上，選取 **流覽** 以選擇資料檔案。

4. 選取資料檔案之後，請指定 **開始日期** ，也可以指定結束日期。

5. 選取開始日期 **之後**，選取 **Upload** 檔案上傳到 CQD。 <br><br>在上傳檔案之前，檔案會經過驗證。 如果驗證失敗，會顯示錯誤訊息，要求您更正檔案。 下圖顯示資料檔案中的欄數不正確時發生錯誤。

   ![顯示建築物資料上傳錯誤的對話方塊範例](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果在驗證期間未發生錯誤，檔案上傳將會成功。 接著，您可以在我的上傳資料表中看到上傳的資料案，顯示該頁面底部目前租使用者所有上傳檔案的完整清單。

> [!NOTE]
> 最多可能需要四小時才能完成建築物檔案的處理。 <br><br> 如果您已經上傳建築物檔案，而且需要新增可能錯過或排除的子網，請新增新的子網來修改原始檔案、移除目前的檔案，然後重新上傳新編輯的檔案。 CQD 中只能有一個使用中的建築物資料檔案。 


## <a name="upload-building-data-file"></a>Upload建資料檔案

CQD 中第一種類型的租使用者資料檔案 **是建築物資料檔案** 。 子網資料行是展開 Network+NetworkRange 資料行，然後將子網資料行加入通話記錄的第一個子網或第二個子網資料行，以顯示建築物、城市、國家/地區或地區資訊。 您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：
  
- 檔案必須是 .tsv 檔案， (欄必須以 TAB) 分隔，或 .csv 檔案 (欄以逗號分隔) 。

- 資料檔案不包含表格標題列。 資料檔案的第一行應該是真正的資料，而不是標題標籤 ，例如「網路」。

- 檔案中的資料類型只能是 String、Integer 或布林值。 對於整數資料類型，值必須是數值。 布林值必須是 0 或 1。

- 如果欄使用 String 資料類型，則資料欄位可以是空白的，但仍必須以索引鍵或逗號分隔。 空白資料欄位只指派空的 String 值。

- 每個租使用者資料檔案有 1，000，000 個展開列限制。

- 每一列必須有 15 個欄，每一欄都必須有適當的資料類型，而且欄的順序必須按照下表 (逗號或定位字元分隔) ：

  **建立資料檔案格式**
  
  | 欄名稱        | 資料類型 | 範例                   | 指導方針              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | 必要              |
  | NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | 需要<sup>1</sup>  |
  | NetworkRange       | 數量    | 26                        | 必要              |
  | BuildingName       | String    | 西雅圖-SEA-1             | 需要<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | 選用              |
  | BuildingType       | String    | IT 終止            | 選用              |
  | BuildingOfficeType | String    | 工程               | 選用              |
  | 城市               | String    | 西雅圖                   | 建議           |
  | 郵遞區號            | String    | 98001                     | 建議           |
  | 國家            | String    | 我們                        | 建議           |
  | 狀態              | String    | 窪                        | 建議           |
  | 地區             | String    | MSUS                      | 建議           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | 必要              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | 必要              |
  | Vpn                | Bool      | 0                         | 選用              |

  <sup>1</sup> 雖然 CQD 不需要，但範本已配置為顯示建築物和網路名稱。

  <sup>2</sup> 此設定可用來反映子網是否位於公司網路內。 您可以自訂其他用途的使用量。

  <sup>3</sup> 此設定可用來反映網路是否使用 Azure ExpressRoute。 您可以自訂其他用途的使用量。  

  **範例列：**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 網路範圍可用來代表一個超網路， (多個子網的組合，以及單一路由首碼) 。 所有新建築物上傳都會檢查是否有重迭範圍。 如果您先前上傳過建置檔案，您應該先下載目前的檔案，然後重新上傳，找出任何重迭之處並修正問題，然後再重新上傳。 先前上傳檔案的任何重迭都可能會導致報告中子網與建築物的相互比對錯誤。 某些 VPN 的實現無法正確報告子網資訊。 
>
> VPN 欄為選擇性，預設為 0。 如果 VPN 欄的值設為 1，該列所代表的子網將會完全展開，以符合子網內的所有 IP 位址。 請謹慎且僅適用于 VPN 子網，因為完全展開這些子網會對建立資料之查詢的查詢時間造成負面影響。 如果子網的擴充導致超過 1，000，000 的擴充列限制，系統將不會接受建房檔案。


### <a name="supernetting"></a>超網路

您可以使用超網路，通常稱為無Inter-Domain路由 (CIDR，) 定義每個子網。 超 *網路* 是多個共用單一路由首碼的子網組合。 您可以不使用每個子網新增專案，而是使用超網路位址。 支援超網路，但我們不建議使用它。

例如，Contoso 的行銷大樓是由下列子網所建立：

-   10.1.0.0/24 -一樓
-   10.1.1.0/24-二樓
-   10.1.2.0/24 -三樓
-   10.1.3.0/24 -四樓

您可以不使用每個子網新增專案，而是使用超網路位址 ，在此範例中為 10.1.0.0/22。

-   Network = 10.1.0.0
-   網路範圍 = 22

以下是在實行超網路之前，請考慮的一些操作：

-   超網路只能用於具有 8 位到 28 位元遮罩的子網映射。

-   超網路佔用較少的前置時間，但代價是降低資料的豐富度。 假設子網 10.1.2.0 發生品質問題。 如果您已實現超網路化，您不會知道子網在建築物中的位置，或網路類型 (例如實驗室) 。 如果您已經定義建築物的所有子網和上傳的樓面位置資訊，就能看到這一區別。

-   請確保超網路位址正確無誤，而且不會捕獲不想要的子網。

-   在資料中尋找 192.168.0.0 是相當常見的。 對於許多組織來說，這表示使用者在家中。 對其他人來說，這是衛星辦公室的 IP 位址方案。 如果貴組織有使用此配置的辦公室，請勿將其納入建築物檔案中，因為使用常見的子網難以區分家用和內部 [網路](quality-of-experience-review-guide.md#common-subnets)。 

> [!IMPORTANT]
> 網路範圍可用來代表超網路。 所有新的建築物資料檔案上傳都會檢查是否有重迭的範圍。 如果您先前上傳過建置檔案，您應該下載目前的檔案，然後再次上傳，找出任何重迭之處並修正問題。 先前上傳檔案的任何重迭都可能會導致子網與報告中建築物的相互比對錯誤。

### <a name="vpn"></a>Vpn

QoE (qoE) 用戶端傳送至 Microsoft 365 或 Office 365 的資料 -這是 CQD 資料的來源地 -包含 VPN 標號。 CQD 會視此為第一個 VPN 和第二個 VPN 維度。 不過，此標號仰賴 VPN 廠商向 Windows註冊的 VPN 網路介面卡是遠端存取介面卡的報告。 並非所有 VPN 廠商都正確註冊遠端存取介面卡。 因此，您可能無法使用內建的 VPN 查詢篩選。 使用上述的 VPN 資料行來正確標記和識別 VPN 子網。 此外，為 VPN 網路貼上標籤也是很好的做法，方便您識別報表。 以下是如何標示 VPN 子網的兩個範例：

- 在 **VPN 子網的** 此欄位中輸入 「VPN」以定義網路名稱。

  ![顯示使用網路名稱的 VPN 的 QCD 報表螢幕擷取畫面](media/qerguide-image-vpnnetworkname.png)

- 在 VPN **子網的** 此欄位中輸入 「VPN」，以定義建築物名稱。

  ![顯示使用建築物名稱的 VPN 的 QCD 報表螢幕擷取畫面](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> 已知 VPN 連接在基礎連接為無線時，會誤判網路連接類型為有線。 當您在 VPN 連接上查看品質時，無法假設已正確識別連線類型。

## <a name="endpoint-data-file"></a>端點資料檔案

另一種類型的 CQD 租使用者資料檔案是 **端點** 資料檔案。 資料行值會用於通話記錄的第一個用戶端端點名稱或第二個用戶端端點名稱欄，以顯示端點建立、模型或類型資訊。 您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：

- 檔案必須是 .tsv 檔案， (欄必須以 TAB) 分隔，或 .csv 檔案 (欄以逗號分隔) 。

- 資料檔案的內容不包含表格標題。 資料檔案的第一行應該是實際資料，而不是標題標籤 ，例如「端點名稱」。

- 所有七欄都只會使用 String 資料類型。 允許的長度上限為 64 個字元。

- 資料欄位可以是空白的，但仍必須以定位字元或逗號分隔。 空白資料欄位只指派空的 String 值。

- 端點名稱必須是唯一的，否則上傳失敗。 如果有重複的一列或兩列使用相同的端點名稱，衝突將導致不正確的聯入。

- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。 它們可以是空白字串或值，例如「IT 部門指定 2018 Laptop」或「資產標記 5678」。

- 每一列必須有七欄，而且欄的順序必須如下：

  **域順序：**

  端點名稱、端點模型、端點模型、端點類型、端點標籤1、端點標籤2、端點標籤3

  **範例列：**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>更新建築物檔案

在收集建築物和子網資訊時，系統管理員通常會在一段時間的多次反覆運算中上傳建築物檔案，並新增新的子網及其建築物資訊。 發生這種情況時，您必須重新上傳建築物檔案。 此程式就像上一節所述的初始上傳，但下列一節所述的少數例外情形除外。

> [!Important]
> 一次只能使用一個建築物檔案。 多個建築物檔案不會累加。

## <a name="add-net-new-subnets"></a>新增淨新子網

有時候，您需要在 CQD 中新增網路新子網，這些子網原本不是網路拓撲的一部分。 若要新增淨新子網，請從 CQD 的租使用者資料 **Upload頁面執行** 下列操作：

1.  如果您還沒有最新版本的檔案，請下載原始檔案。

1.  移除 CQD 中的目前檔案。

1.  編輯原始建築物檔案，並提供在取得新子網之前至少一天的結束日期。

1.  將淨新子網附加到原始建築物檔案。

1.  Upload新修改的建築物檔案，並設定前一個建築物檔案結束後一天的開始日期。

## <a name="add-missing-subnets"></a>新增遺失的子網

上傳受管理網路的建築物資訊之後，每個受管理網路都應該有建築物關聯。 不過，情況不一定一定如此;通常會漏接幾個子網。 若要尋找這些遺失的網路，請檢閱 CQD 中體驗品質 **報告頁面上的** 遺失子網報告。 這會以 10 或多個音訊資料流程呈現所有子網，這些音訊流未在建築物資料檔案中定義，而且標示為外部。 請在此清單中確保沒有受管理網路。 如果子網遺失，請使用下列程式更新原始建築物資料檔案，然後重新上傳至 CQD。

1. 前往 CQD **Upload** 租使用者資料頁面。

1. 如果您還沒有最新版本的檔案，請下載原始檔案。

1. 移除 CQD 中的目前檔案。

1. 將新的子網附加到原始檔案。

1. Upload建立檔案。 請務必將開始日期設定為至少八個月之前，讓 CQD 處理歷史資料。


> [!IMPORTANT]
> 您必須將租使用者識別碼新增為第二個租使用者識別碼的查詢篩選，才能篩選報表，只查看貴組織的租使用者資料。 否則，報表會顯示聯盟子網。

> [!NOTE] 
> 請務必將月年報表篩選調整為目前月份。 選取 **編輯**，然後調整月 **年** 報表篩選以儲存新的預設月份。


## <a name="related-topics"></a>相關主題

[建立 CQD 的建築物地圖](CQD-building-mapping.md)

[改善及監控通話品質Teams](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)
