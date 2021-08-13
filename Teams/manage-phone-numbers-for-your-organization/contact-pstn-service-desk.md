---
title: 聯絡 PSTN 服務台
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.pstnservicedesk
- ms.teamsadmincenter.voice.contactPSTNsupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: 當您取得貴組織的電話號碼或移轉 (傳輸) 號碼時，您可能需要在 PSTN 服務台取得協助和支援。
ms.openlocfilehash: 4fa1a72c68c43f82715fb5f54a77a2e3a2181445f37afeb4f1bf640bb2766de6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310671"
---
# <a name="pstn-service-desk"></a>PSTN 服務台 

有一個與 PSTN 服務台互動的新流程。 現在，您可以使用 Teams 系統管理中心整合的單一位置開啟票券、查看票券並追蹤通訊。 本文說明了與服務台聯繫的一切須知事項。

> [!NOTE]
> 自 2021 年 7 月 22 日起，目前的電子郵件系統已遭淘汰。

若要聯絡服務台：

1. 登入您的 Teams 系統管理中心 - admin.teams.microsoft.com。

2. 在左側窗格中，選取 **[電話號碼]**。

3. 在頁面頂端，選取 **[取得電話號碼支援]**。 您將看到 [電話號碼服務中心]。  

> [!NOTE]
> 只允許來自相同租使用者的人員建立案例。 也就是說，來自 @fabrikam.com 的某人無法代表 @contoso.com 建立案例。 

您可以從 [電話號碼服務中心] 建立新案例、查看現有案例、與服務台通訊，以及管理您的使用者設定檔。下列各節會詳細說明這些工作。

- **[電話號碼服務中心]** – 瀏覽至 [入口網站] 首頁。 

- **[[建立新案例]](#create-a-new-case)** – 提交新要求或一般諮詢。 

- **[[檢視我現有的案例]](#view-and-manage-existing-cases)** - 追蹤並監視您現有的案例。 

- **[[檢視我公司的案例]](#view-and-manage-existing-cases)**  - 追蹤並監視貴公司現有的案例。 如果貴公司的同事已開啟任何案例，您可以在此視圖中查看這些案例。  

- **[[給予意見反應]](#view-and-manage-existing-cases)** - 請與我們分享您的意見反應。 

- **[您的名稱]**  - 更新您的設定檔頁面。 


## <a name="create-a-new-case"></a>建立新案例

若要建立新案例，請遵循下列步驟：

1. 從下列其中一個地方，選取 **[建立新案例]**：  

   - 從 **[電話號碼服務中心]** 頁面、頁面頂端或底部磚。

   - 從 **[檢視我現有的案例]** 頁面。

   - 從 **[檢視我公司的案例]** 頁面。

2. 請提供您的案例詳細資料，如 [下一節](#provide-case-details) 所述。

3. 輸入所有值之後，選取 **[提交]**。 您將看到新的畫面，您可以在其中看到案例編號。  

### <a name="provide-case-details"></a>提供案例詳細資料

若要瞭解案例詳細資料，Microsoft 需要下列資訊：

- [案例類別](#case-category)
- [國家或區域](#country-or-region)
- [案例類型](#case-type)
- [案例標題](#case-title)
- [通知的其他連絡人](#additional-contacts-for-notifications)
- [描述](#description)
- [其他支援文件](#additional-supporting-documents)

#### <a name="case-category"></a>案例類別

案例可以有兩個類別之一： 

- **[提交新要求]** - 如果您想要提交新要求，請選擇此選項。 例如，您想要提交移轉要求，或想要向 Microsoft 購買電話號碼。  

- **[一般諮詢]** - 如果您有問題，請選擇此選項，這可協助判斷您的要求。 例如，您必須知道您是否可以將無線號碼移轉到 Microsoft，或者您需要知道 Microsoft 是否支援替代免付費電話號碼。 

#### <a name="country-or-region"></a>國家或地區

選取您提交此案例的國家/地區。 如果您有多個國家/地區的要求，您必須為每個國家/地區開啟一個案例。  

#### <a name="case-type"></a>案例類型

案例類型可以是下列其中一項：

- **自訂通話名稱 (僅適用于美國)** - 在 Microsoft 電話號碼上設定自訂通話名稱。 這僅適用于美國電話號碼。 

  - **設定自訂通話名稱 (僅 15 個字元)** - 您想要設定的自訂通話名稱。 名稱上限為 15 個字元。  

  - **電話號碼清單** - 您想要設定自訂通話名稱值的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。  

- **租使用者移轉**– 將電話號碼從一個租使用者移轉到另一個租使用者。 例如，Microsoft 內有兩個不同的租使用者，而您想要將電話號碼從一個租使用者移動到另一個租使用者。  

  - **來源租使用者網域名稱** - 您想要將電話號碼移至不同租使用者的來源租使用者。  

  - **來源租使用者唯一識別碼** - 來源租使用者的租使用者識別碼。 這是選擇性欄位。  

  - **目的地租使用者網域名稱** - 您想要將電話號碼移動到的租使用者。  

  - **目的地租使用者唯一識別碼** - 目的地租使用者的租使用者識別碼。 這是選擇性欄位。  

  - **要求的日期時間*** - 您希望號碼從來源租使用者移動至目的地租使用者的日期與時間。 查看日期及時間。

  - **電話號碼清單** - 您想要從來源租使用者移動至目的地租使用者的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。 

- **庫存類型變更** – 變更電話號碼類型。 例如，您想要將 Microsoft 訂閱者號碼變更為服務號碼。 如需 Microsoft 支援的電話號碼類型詳細資訊，請參閱 [[電話號碼類型]](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **轉換成** - 選取以將您的號碼轉換成使用者號碼或服務號碼。 

  - **偏好的日期/時間*** - 您想要變更號碼的庫存類型的日期和時間。 請參閱日期和時間以瞭解詳細資訊。

  - **核取方塊 - 我瞭解，若要更新庫存類型，必須取消指派我的電話號碼** - Microsoft 無法處理電話號碼類型變更要求，除非您租使用者內的電話號碼未遭指派。 如果您要求對未來日期進行這項變更，則您必須確定號碼在要求的日期及時間之前未遭指派。 

  - **電話號碼清單** - 您想要變更其類型的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。 

- **新 TN 購買** - 向 Microsoft 購買新電話號碼。  

  - **號碼類型** - 選取號碼的類型。 請參閱 [[電話號碼類型]](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **嘗試從 Teams 系統管理中心入口網站取得電話號碼** - 您是否嘗試從 Microsoft Teams 系統管理中心入口網站 (您可於此使用自助服務) 購買這些電話號碼？  

  - **所需的電話號碼數量** - 您想要購買的電話號碼數量。  

  - **州/省** - 您想要電話號碼的國家/地區內的州/省。  

  - **城市** - 您想要電話號碼的州/省內城市。  

  - **辦公室位址** - 僅適用于特定國家/地區。 這是您辦公室的網站位址。  

  - **目錄清單** - 僅適用于特定國家/地區。 是否要使用電話號碼發佈您的公司資訊？  

- **移轉入** – 將現有電話號碼從目前的服務提供者移轉到 Microsoft。  

  - **為您的移轉訂單命名** - 提供容易記住的連接埠要求名稱。 

  -  **要求移轉日期/時間*** - 您希望號碼移轉到 Microsoft 的日期和時間。 請注意，這不是保證的移轉日期，因為目前的號碼擁有者必須先核准我們的移轉要求。 查看日期及時間。 

  - **移轉號碼清單** - 要移轉到 Microsoft 的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。 

  - **授權委託書 (LOA)** - 在這裡附加已簽署且填寫的 LOA。 Microsoft 無法處理沒有 LOA 的移轉要求。  

- **位址更新**– 更新緊急通話位址。 請注意，此欄位僅適用于特定國家/地區。 

  - **位置識別碼** - 緊急位址的位置識別碼。 

  - **電話號碼清單** - 您想要變更緊急位址的電話號碼清單 (在描述欄位中輸入您想要的位址)。 上傳包含電話號碼清單的 csv 檔案。 

***日期及時間。** 如果您選取國家/地區 = 法國，日期 = 2021 年 8 月 14 日，時間 = 上午 10 點，則要求將在 2021 年 8 月 14 日上午 10 點執行。 法國時間。 

#### <a name="case-title"></a>案例標題

輸入摘要您的問題的標題。  

#### <a name="additional-contacts-for-notifications"></a>通知的其他連絡人

輸入將接收 Microsoft 自動狀態通知之人員清單。 例如，您想要下單移轉入訂單，且除了您自己之外，還希望有其他兩名同事能接收自動狀態通知。 在 **通知電子郵件** 區段提供同事的電子郵件地址。 這是選擇性資訊。 

#### <a name="description"></a>描述

描述您嘗試達成的目標，並列出您對於 Microsoft PSTN 服務台的問題。  

#### <a name="additional-supporting-documents"></a>其他支援文件

上傳您案例的其他文件。  

## <a name="view-and-manage-existing-cases"></a>查看及管理現有案例

您可以選取 **[檢視我的現有案例]**，然後選取案例編號，以檢視您的案例。 選取案例編號會將您重新導向至案例詳細資料。 (您也可以選取 **[檢視公司案例]**，以檢視公司案例。)您也可以：

- 選取 **[開啟案例]**、**[所有案例]** 或 **[已關閉案例]** 來 **篩選您的案例**。

- 開啟現有的案例、向下卷動，並選取 **[新增註解]**，以針對您的案例，**與 PSTN 服務台通訊**。 將會顯示新視窗。 在註解方塊中輸入您的訊息。 附加任何可協助您處理要求的支援文件 (如果有)，然後選取 **[提交]**。  

  PSTN 服務台的回應將會顯示在相同的時間表下。 當您的案例中有更新時，您將會收到更新的自動電子郵件通知。 

- 瀏覽至現有案例、向下卷動，並選取 **[取消案例]**，以 **取消案例**。 從下拉式清單中選取取消的原因，然後選取 **[取消]**。  

- **[解決案例]** - 如果您認為您的要求已完成，您可以瀏覽至現有的案例、向下卷卷並選取 **[解決案例]**。 選取 **[關閉]**；案例現在會顯示為 **[已解決 – 問題解決]**。  


## <a name="related-topics-and-additional-resources"></a>相關主題與其他資源

- 如需有關號碼安裝和設定、授權、費用或計費的協助，請參閱 [[商務產品的支援連絡 - 系統管理協助]](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。

- 如需您的國家或地區可使用的通話方案的資訊，請參閱[[音訊會議與通話方案的適用國家/地區]](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

- 如需可協助您為貴組織選取適當電話號碼類型的資訊，請參閱 [[不同類型的電話號碼]](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

- 如需管理貴組織的電話號碼的資訊，請參閱 [[管理貴組織的電話號碼]](manage-phone-numbers-for-your-organization.md)。

- 如需緊急通話條款及條件的資訊，請參閱 [[緊急通話的條款及條件]](../emergency-calling-terms-and-conditions.md)。
