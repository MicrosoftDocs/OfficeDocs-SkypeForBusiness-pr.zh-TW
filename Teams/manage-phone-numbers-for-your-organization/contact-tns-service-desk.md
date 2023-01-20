---
title: 連絡電話號碼服務小組
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: 當您取得組織的電話號碼或埠 (移轉) 號碼時，您可能需要在 TNS 服務台取得協助及支援。
ms.openlocfilehash: 9984775a05458592fe1789c0dd8b173a08783220
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835556"
---
# <a name="telephone-number-services-tns---service-desk"></a>電話號碼服務 (TNS) - 服務台

> [!NOTE]
> 自 2021 年 7 月 22 日起，先前要連絡 TNS 服務台的電子郵件系統已停用。

有一個新的程式可以從我們新的電話號碼 **[服務中心](https://pstnsd.powerappsportals.com)** 與電話號碼服務 (TNS) 服務台互動。 現在，您可以使用 Teams 系統管理中心整合的單一位置開啟票券、查看票券並追蹤通訊。 下列各節會詳細說明這些工作。


- **[建立新案例](#create-a-new-case)** ： 提交新要求或一般查詢。

- **[檢視我現有的案例](#view-and-manage-existing-cases)** ： 追蹤及監控現有案例 (的) 。

- **[檢視我的公司案例](#view-and-manage-existing-cases)** - 追蹤及監控公司現有的案例 () 。 如果貴公司的同事已開啟任何案例，您可以在此視圖中查看這些案例。

- **[提供意見](#view-and-manage-existing-cases)** 反應：與我們分享您的意見反應。

## <a name="create-a-new-case"></a>建立新案例

> [!NOTE]
> 只有來自相同租使用者的人員才能建立案例。 例如，來自 @fabrikam.com 的人無法代表 @contoso.com 建立案例。

若要建立新案例，請遵循下列步驟：

1. 從下列其中一個地方，選取 **[建立新案例]**：

   - 從 **[電話號碼服務中心** ] 首頁，在頁面頂端或底部磚。

   - 從 **[檢視我現有的案例]** 頁面。

   - 從 **[檢視我公司的案例]** 頁面。

2. 請提供您的案例詳細資料，如 [下一節](#provide-case-details) 所述。

3. 輸入所有值之後，選取 [ **提交]**。 您會看到新的畫面，您可以在其中看到您的案例編號。

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

- **一般查詢** - 如果您有任何問題可協助您判斷您的要求，請選擇此選項。 例如，您必須知道您是否可以將無線號碼移轉到 Microsoft，或者您需要知道 Microsoft 是否支援替代免付費電話號碼。

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

  - **核取方塊 – 我瞭解為了能夠更新庫存類型，我的電話號碼必須取消指派** - 除非未指派您租使用者中的電話號碼，否則 Microsoft 無法處理電話號碼類型變更要求。 如果您要求對未來日期進行這項變更，則您必須確定號碼在要求的日期及時間之前未遭指派。

  - **電話號碼清單** - 您想要變更其類型的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。

- **新 TN 購買** - 向 Microsoft 購買新電話號碼。

  - **號碼類型** - 選取號碼的類型。 請參閱 [[電話號碼類型]](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **嘗試從 Teams 管理員 中心入口網站取得電話號碼**- 您是否已嘗試從 Microsoft Teams 管理員中心購買這些電話號碼？

  - **所需的電話號碼數量** - 您想要購買的電話號碼數量。

  - **州/省** - 您想要電話號碼的國家/地區內的州/省。

  - **城市** - 您想要電話號碼的州/省內城市。

  - **辦公室位址** - 僅適用于特定國家/地區。 這是您辦公室的網站位址。

  - **目錄清單** - 僅適用于特定國家/地區。 是否要使用電話號碼發佈您的公司資訊？

- **移轉入** – 將現有電話號碼從目前的服務提供者移轉到 Microsoft。

  - **為您的移轉訂單命名** - 提供容易記住的連接埠要求名稱。

  - **要求移轉日期/時間*** - 您希望號碼移轉到 Microsoft 的日期和時間。 目前的數位擁有者必須先核准我們的移轉要求，因此無法保證移轉日期。 查看日期及時間。

  - **移轉號碼清單** - 要移轉到 Microsoft 的電話號碼清單。 上傳包含電話號碼清單的 csv 檔案。

  - **授權委託書 (LOA)** - 在這裡附加已簽署且填寫的 LOA。 Microsoft 無法處理沒有 LOA 的移轉要求。

    > [!NOTE]
    > 如需有關用於移轉現有電話號碼及其他檔需求的 LOAs 詳細資訊，請參閱 [管理通話方案的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。
    >
    >若要為使用者移轉/移轉 999 個或更少的電話號碼，請在 Microsoft Teams 系統管理中心上傳已完成和簽署的 LOAs，以進一步處理。
    >
    > 若要移轉/移轉超過 999 個電話號碼，或如果您在 Microsoft Teams 系統管理中心發生移轉程式問題，您可以 [手動將移轉訂單提交](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) 給您地區的 TNS 服務台。

- **位址更新**– 更新緊急通話位址。 請注意，此欄位僅適用于特定國家/地區。

  - **位置識別碼** - 緊急位址的位置識別碼。

  - **電話號碼清單** - 您想要變更緊急位址的電話號碼清單 (在描述欄位中輸入您想要的位址)。 上傳包含電話號碼清單的 csv 檔案。

**日期及時間。** 如果您選取國家/地區 = 法國，日期 = 2021 年 8 月 14 日，時間 = 上午 10 點，則要求將在 2021 年 8 月 14 日上午 10 點執行。 法國時間。

#### <a name="case-title"></a>案例標題

輸入摘要您的問題的標題。

#### <a name="additional-contacts-for-notifications"></a>通知的其他連絡人

輸入將接收 Microsoft 自動狀態通知之人員清單。
例如，您想要下單移轉入訂單，且除了您自己之外，還希望有其他兩名同事能接收自動狀態通知。 在 **通知電子郵件** 區段提供同事的電子郵件地址。 這是選擇性資訊。

#### <a name="description"></a>描述

描述您嘗試達成的目標，並列出您對於服務台 TNS (Microsoft 電話號碼服務的問題) 。

#### <a name="additional-supporting-documents"></a>其他支援文件

上傳您案例的其他文件。

## <a name="view-and-manage-existing-cases"></a>查看及管理現有案例

您可以選取 **[檢視我的現有案例]**，然後選取案例編號，以檢視您的案例。 選取案例編號會將您重新導向至案例詳細資料。 (您也可以選取 **[檢視公司案例]**，以檢視公司案例。)您也可以：

- 選取 **[開啟案例]**、**[所有案例]** 或 **[已關閉案例]** 來 **篩選您的案例**。

- 開啟現有大小寫、向下捲動，然後選取 [**新增批註**]，**與 TNS 服務台** 就您的案例進行溝通。 將會顯示新視窗。 在註解方塊中輸入您的訊息。 附加任何支援檔 (如果有的話) ，然後選取 [ **提交]**。

  **來自 TNS 服務台的** 回應會顯示在相同的時程表下方。 當您的案例中有更新時，您將會收到更新的自動電子郵件通知。

- 瀏覽至現有案例、向下卷動，並選取 **[取消案例]**，以 **取消案例**。 從下拉式清單中選取取消的原因，然後選取 **[取消]**。

- **[解決案例]** - 如果您認為您的要求已完成，您可以瀏覽至現有的案例、向下卷卷並選取 **[解決案例]**。 選取 **[關閉]**；案例現在會顯示為 **[已解決 – 問題解決]**。

## <a name="related-topics-and-additional-resources"></a>相關主題與其他資源

- 如需有關號碼安裝和設定、授權、費用或計費的協助，請參閱 [[商務產品的支援連絡 - 系統管理協助]](/microsoft-365/admin/contact-support-for-business-products?tabs=online)。

- 如需您的國家或地區可使用的通話方案的資訊，請參閱[[音訊會議與通話方案的適用國家/地區]](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

- 如需貴組織適用類型的 () 電話號碼的相關資訊，請參閱 [不同類型的電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

- 如需管理貴組織的電話號碼的資訊，請參閱 [[管理貴組織的電話號碼]](manage-phone-numbers-for-your-organization.md)。

- 如需緊急通話條款及條件的資訊，請參閱 [[緊急通話的條款及條件]](../emergency-calling-terms-and-conditions.md)。
