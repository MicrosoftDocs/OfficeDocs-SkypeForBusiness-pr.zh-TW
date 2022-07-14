---
title: 在 [通話品質儀表板] (CQD) 中上傳租使用者和建築物資料
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何在 [通話品質儀表板] (CQD) 中上傳租使用者和建置資料。
ms.openlocfilehash: d9559490aa990f3df800e0e9438810c63d153d3c
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789638"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>在 [通話品質儀表板] (CQD) 中上傳租使用者和建築物資料


若要充分利用 [通話品質儀表板] (CQD) ，建議您上傳租使用者和建築物資料。 有 2 種類型的租使用者資料檔： [建築物](#upload-building-data-file) 和 [端點](#endpoint-data-file)。

您可以 [在這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例租使用者資料範本。 如需建置對應的說明，請參閱 [建立 CQD 的建築物地圖](CQD-building-mapping.md)。

從 CQD 摘要報告儀表板中，選取 [CQD **設定**] 功能表中的 [**租使用者資料上傳**]， (CQD) 頂端的齒輪圖示。 從這裡，系統管理員可以上傳組織的建築物和端點資訊，例如 IP 位址和地理位置資訊的對應、對應每個無線存取點及其 MAC 位址等。

1. 從 Teams 系統管理中心或在 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 開啟 CQD (，然後選取右上角的齒輪圖示，然後從 [**摘要報告**] 頁面選擇 [**租使用者資料上傳**]。

   ![上傳資料時出現的對話方塊螢幕擷取畫面。](media/qerguide-image-tenantdataupload.png)
    
2. 或者，如果這是您第一次造訪 CQD，系統也會要求您上傳建築物資料。 您可以選取 **[立即上傳]** ，快速流覽至 [ **租使用者資料上傳** ] 頁面。

   ![通知使用者上傳建築物資料之橫幅的螢幕擷取畫面。](media/qerguide-image-buildingdatauploadbanner.png)

3. 在 [ **租使用者資料上傳** ] 頁面上，選取 [ **流覽** ] 以選擇資料檔案。

4. 選取資料檔案後，指定 **開始日期** ，並選擇性地指定結束日期。

5. 選取 **[開始日期**] 之後，選取 **[上傳** ] 將檔案上傳到 CQD。 <br><br>檔案上傳之前，會先進行驗證。 如果驗證失敗，會顯示錯誤訊息，要求您更正檔案。 下圖顯示資料檔中的欄數不正確時發生錯誤。

   ![顯示建築物資料上傳錯誤的對話方塊範例。](media/qerguide-image-buildingdatauploaderror.png)
 
6. 如果驗證期間沒有發生任何錯誤，則檔案上傳將會成功。 接著，您可以在 [ **我的上傳** ] 資料表中看到上傳的資料檔，該資料表會在該頁面底部顯示目前租使用者所有已上傳檔案的完整清單。

> [!NOTE]
> 完成處理建築物檔案最多可能需要四個小時。 <br><br> 如果您已上傳建築物檔案，而且需要新增可能已遺漏或排除的子網，請新增新的子網來修改原始檔案、移除目前的檔案，然後重新上傳新編輯的檔案。 CQD 中只能有一個使用中的建築物資料檔。 


## <a name="upload-building-data-file"></a>上傳建築物資料檔

CQD 中的第一種租使用者資料檔案類型是 **「建築物** 」資料檔案。 子網資料行是藉由展開 Network+NetworkRange 資料行，然後將 Subnet 欄加入通話記錄的第一個子網或第二個子網欄以顯示建築物、城市、國家/地區或地區資訊來衍生。 您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：
  
- 檔案必須是 .tsv 檔案， (欄是以 TAB) 分隔，或是.csv檔案， (欄以逗號) 分隔。

- 資料檔案不包含表格標題列。 資料檔案的第一行是實際資料，而不是像是「網路」這樣的標頭標籤。

- 檔案中的資料類型只能是 String、Integer 或 Boolean。 對於整數資料類型，值必須是數值。 布林值必須為 0 或 1。

- 如果資料行使用 String 資料類型，則資料欄位可以是空白的，但仍必須以索引標籤或逗號分隔。 空白資料欄位只會指派空字串值。

- 每個租使用者資料檔有 1，000，000 個展開的列數限制。

- 每一列必須有 15 欄，每一欄都必須有適當的資料類型，而且必須按照下表中列出的順序 (逗號或定位字元分隔) ：

  **建置資料檔案格式**
  
  | 欄名稱        | 資料類型 | 範例                   | 指導方針              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | 必要              |
  | NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | 需要<sup>1</sup>  |
  | NetworkRange       | 數量    | 26                        | 必要              |
  | BuildingName       | String    | SEATTLE-SEA-1             | 需要<sup>1</sup>  |
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
  | VPN                | Bool      | 0                         | 選用              |

  <sup>1</sup> 雖然 CQD 不需要，但範本已設定為顯示建築物和網路名稱。

  <sup>2</sup> 此設定可用來反映子網是否在公司網路內。 您可以針對其他用途自訂使用量。

  <sup>3</sup> 此設定可用來反映網路是否使用 Azure ExpressRoute。 您可以針對其他用途自訂使用量。  

  **範例列：**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 網路範圍可用來表示數個子網的超級網路 (組合，以及單一路由前置詞) 。 所有新的建築物上傳都會檢查是否有任何重迭的範圍。 如果您先前已上傳建築物檔案，您應該下載目前的檔案並重新上傳，以找出任何重迭專案並修正問題，再重新上傳。 先前上傳的檔案中的任何重迭可能會導致報表中子網對應到建築物的錯誤。 某些 VPN 實作不會正確回報子網資訊。 
>
> VPN 欄為選用，預設為 0。 如果 VPN 欄的值設為 1，該列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。 請謹慎使用此功能，而且僅適用于 VPN 子網，因為完全展開這些子網會對涉及建置資料的查詢時間產生負面影響。 如果子網的擴充會導致超過 1，000，000 的展開列限制，則不會接受建築物檔案。


### <a name="supernetting"></a>Supernetting

您可以使用超級網路，通常稱為無類別Inter-Domain路由 (CIDR，) 來取代每個子網。 *超級網路* 是數個子網的組合，這些子網共用單一路由首碼。 您可以使用超網位址，而不是為每個子網新增專案。 支援 Supernetting，但我們不建議使用它。

例如，Contoso 的行銷大樓是由下列子網所組成：

-   10.1.0.0/24 - 第一樓
-   10.1.1.0/24 - 二樓
-   10.1.2.0/24 - 三樓
-   10.1.3.0/24 - 四樓

您可以使用此範例 10.1.0.0.0/22 中的超網路位址，而不是為每個子網新增專案。

-   Network = 10.1.0.0
-   網路範圍 = 22

以下是實作超級網路之前必須考慮的一些事項：

-   Supernetting 只能在具有 8 位到 28 位遮罩的子網對應中使用。

-   上線需要較少的時間，但要降低資料的豐富性是需要付出的成本。 假設子網 10.1.2.0 有品質問題。 如果您實作超級網路，您將不知道子網建置的位置，或是 (的網路類型，例如實驗室) 。 如果您定義了建築物的所有子網，並上傳了樓面位置資訊，您就能看到該區別。

-   請務必確保超網路位址正確無誤，而且不會找到不想要的子網。

-   經常在資料中尋找 192.168.0.0。 對許多組織來說，這表示使用者在家。 對其他人而言，這是衛星辦公室的 IP 位址配置。 如果貴組織確實有使用此設定的辦公室，請勿將它包含在您的建築物檔案中，因為使用 [一般子網](quality-of-experience-review-guide.md#common-subnets)難以區分家庭和內部網路。 

> [!IMPORTANT]
> 網路範圍可用來代表超級網路。 所有新的建築物資料檔上傳都會檢查是否有任何重迭的範圍。 如果您先前已上傳建築物檔案，您應該下載目前的檔案並再上傳一次，以找出任何重迭專案並修正問題。 先前上傳的檔案中的任何重迭可能會導致報表中子網對應到建築物的錯誤。

### <a name="vpn"></a>VPN

用戶端傳送至 Microsoft 365 或 Office 365 之 QoE) 資料 (體驗品質，也就是 CQD 資料的來源位置，都包含 VPN 標幟。 CQD 會將此視為第一個 VPN 和第二個 VPN 維度。 不過，此旗標需仰賴 VPN 廠商向 Windows 報告註冊的 VPN 網路介面卡是遠端存取介面卡。 並非所有 VPN 廠商都能正確註冊遠端存取介面卡。 因此，您可能無法使用內建的 VPN 查詢篩選。 使用上述討論的 VPN 欄來精確標記及識別 VPN 子網。 也建議您為 VPN 網路加上標籤，以便在報告中輕鬆識別。 以下是為 VPN 子網加上標籤的兩個範例：

- 在此欄位中輸入 VPN 子網的 [VPN] 來定義網路 **名稱** 。

  ![顯示使用網路名稱之 VPN 的 QCD 報告螢幕擷取畫面。](media/qerguide-image-vpnnetworkname.png)

- 在此欄位中輸入 VPN 子網的 「VPN」來定義 **建築物名稱** 。

  ![QCD 報告螢幕擷取畫面，顯示使用建築物名稱的 VPN。](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> 已知 VPN 連線在基礎連線為無線時，誤認為網路連線類型為有線。 透過 VPN 連線查看品質時，您無法假設已正確識別連線類型。

## <a name="endpoint-data-file"></a>端點資料檔案

另一種類型的 CQD 租使用者資料檔案是 **端點** 資料檔案。 資料行值會用於通話記錄的第一個用戶端點名稱或第二個用戶端端點名稱欄，以顯示端點製作、模型或類型資訊。 您上傳的資料檔案格式必須符合下列準則，才能在上傳前通過驗證檢查：

- 檔案必須是 .tsv 檔案， (欄是以 TAB) 分隔，或是.csv檔案， (欄以逗號) 分隔。

- 資料檔案的內容不包含表格標題。 資料檔案的第一行應為實際資料，而非像是「端點名稱」的頁首標籤。

- 所有七欄僅使用字串資料類型。 允許的長度上限為 64 個字元。

- 專案會區分大小寫;EndpointName **ABC123** 會從 EndpointName **abc123** 視為唯一。

- 資料欄位可以是空白的，但仍必須以索引標籤或逗號分隔。 空白資料欄位只會指派空字串值。

- EndpointName 必須是唯一的，否則上傳失敗。 如果有重複的列或兩列使用相同的 EndpointName，衝突會造成不正確的連接。

- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。 它們可以是空字串或值，例如「IT 部門指定的 2018 Laptop」或「資產標籤 5678」。

- 每一列必須有七欄，而且欄必須按照下列順序排列：

  **域順序：**

  EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **範例列：**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>更新建築物檔案

在收集建築物和子網資訊時，系統管理員通常會在一段時間後以多個反覆運算方式上傳建築物檔案，並在可用時新增子網及其建築物資訊。 發生這種情況時，您需要重新上傳您的建築物檔案。 此程式就像上一節所述的初始上傳，但下一節中有一些例外。

> [!Important]
> 一次只能使用一個建築物檔案。 多個建築物檔案並非累積。

## <a name="add-net-new-subnets"></a>新增網路子網

有時候您需要將原本不是您網路拓撲一部分的淨新子網新增至 CQD。 若要新增 net 新子網，請從 CQD 的 **[租使用者資料上傳** ] 頁面執行下列操作：

1.  如果您還沒有最新的複本，請下載原始檔案。

1.  在 CQD 中移除目前的檔案。

1.  編輯原始的建築物檔案，並提供至少要在取得 net 新子網前一天的結束日期。

1.  將網路新子網附加到原始的建築物檔案。

1.  上傳新修改的建築物檔案，並設定前一個建築物檔案結束後一天的開始日期。

## <a name="add-missing-subnets"></a>新增遺失的子網

在您上傳受管理網路的建築物資訊之後，每個受管理的網路都應該有建築物關聯。 不過，這種情況不一定都能發生;通常會遺漏一些子網。 若要尋找這些遺失的網路，請在 CQD **的 [體驗品質報告**] 頁面上檢閱遺 **失的子網報告**。 這會以 10 個以上的音訊串流呈現所有子網，這些資料流程未在建築物資料檔中定義且標示為外部。 確定此清單中沒有受管理的網路。 如果子網遺失，請使用下列程式來更新原始的建築物資料檔，並將它重新上傳到 CQD。

1. 移至 CQD 中的 **[租使用者資料上傳** ] 頁面。

1. 如果您還沒有最新的複本，請下載原始檔案。

1. 在 CQD 中移除目前的檔案。

1. 將新的子網附加到原始檔案。

1. 上傳建築物檔案。 請務必將開始日期設定為至少八個月前，讓 CQD 處理歷史資料。


> [!IMPORTANT]
> 您必須將您的租使用者識別碼新增為第 **二個租使用者標識** 符的查詢篩選器，以篩選報表以僅檢視貴組織的租使用者資料。 否則，報告會顯示同盟子網。

> [!NOTE] 
> 請務必將月份年度報表篩選調整為目前月份。 選取 **[編輯**]，然後調整 **[月份年** ] 報表篩選以儲存新的預設月份。


## <a name="related-topics"></a>相關主題

[建立 CQD 的建築物地圖](CQD-building-mapping.md)

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定呼叫品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)
