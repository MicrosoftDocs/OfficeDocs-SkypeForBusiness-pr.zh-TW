---
title: 連上 PSTN 服務台
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
description: 當您取得電話號碼或 (轉接) ，您可能需要在 PSTN 服務台取得協助和支援。
ms.openlocfilehash: b3925fbd473094b06133fb7cfe31479396434b80
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510274"
---
# <a name="pstn-service-desk"></a>PSTN 服務台 

有一個新的程式可以與 PSTN 服務台互動。 現在，您可以在與系統管理中心整合的單一位置開啟票證、Teams及追蹤通訊。 本文將說明您聯絡服務台所需的一切資訊。

> [!NOTE]
> 自 2021 年 7 月 22 日起，目前的電子郵件系統已停用。

若要與服務台聯繫：

1. 登入您的 Teams 系統管理中心 - admin.teams.microsoft.com。

2. 在左側窗格中，選取 電話 **數位**。

3. 在頁面頂端，選取 取得 **電話號碼支援**。 您會看到號碼服務中心電話號碼服務中心。  

> [!NOTE]
> 只有來自同一租使用者的人才能建立案例。 也就是說，來自 @fabrikam.com 的人無法代表 @contoso.com。 

從 電話服務中心，您可以建立新案例、查看現有案例、與服務台通訊，以及管理您的使用者設定檔。 下列各節將詳細說明這些工作。

- **電話號碼服務中心**  – 流覽至入口網站首頁。 

- **[建立新案例](#create-a-new-case)**  – 提交新要求或一般查詢。 

- **[查看我現有的案例](#view-and-manage-existing-cases)** - 追蹤並監控現有案例 () 。 

- **[查看我的公司案例](#view-and-manage-existing-cases)**  – 追蹤並監控您公司現有的案例 () 。 如果您的公司同事已開啟任何案例，您可以在此視圖中查看這些案例。  

- **[提供意見回饋](#view-and-manage-existing-cases)**– 與我們分享您的意見。 

- **[您的名稱]**  – 更新您的個人資料頁面。 


## <a name="create-a-new-case"></a>建立新案例

若要組織新案例，請遵循下列步驟：

1. 從 **下列其中一個地方** 選取建立新案例：  

   - 從 電話 **號碼服務中心** 頁面、頁面頂端或底部磚。

   - 從查看 **我現有的案例頁面**  。

   - 從查看 **我的公司案例** 頁面。

2. 提供您的案例詳細資料，如下一節[所述。](#provide-case-details)

3. 輸入所有值之後，選取 **提交**。 您會看到一個新的畫面，您可以在其中看到您的案例編號。  

### <a name="provide-case-details"></a>提供案例詳細資料

若要瞭解案例詳細資料，Microsoft 需要下列資訊：

- [案例類別](#case-category)
- [國家或地區](#country-or-region)
- [大小寫類型](#case-type)
- [大小寫標題](#case-title)
- [其他通知連絡人](#additional-contacts-for-notifications)
- [描述](#description)
- [其他支援檔](#additional-supporting-documents)

#### <a name="case-category"></a>案例類別

案例可以有兩種類別之一： 

- **提交新要求**- 如果您想要提交新要求，請選擇這個選項。 例如，您想要提交埠要求，或想要向 Microsoft 購買電話號碼。  

- **一般查詢** - 如果您有問題可協助判斷您的要求，請選擇這個選項。 例如，您必須知道您是否可以將無線號碼移植到 Microsoft，或您必須知道 Microsoft 是否支援虛名免付費號碼。 

#### <a name="country-or-region"></a>國家或地區

選取要提交此案例的國家/地區。 如果您有多個國家/地區的要求，您必須針對每個國家/地區開啟一個案例。  

#### <a name="case-type"></a>大小寫類型

大小寫類型可以是下列其中一種：

- **自訂通話 (美國**) - 在 Microsoft 電話號碼上設定自訂通話名稱。 這僅適用于美國電話號碼。 

  - **自訂通話名稱， (15 個字元**) 字元 - 這是您想要設定自訂的通話名稱。 名稱的上限為 15 個字元。  

  - **電話號碼清單** - 這是要設定自訂通話名稱值的電話號碼清單。 Upload包含電話號碼清單的 csv 檔案。  

- **租使用者間埠** ： 將電話號碼從一個租使用者移到另一個租使用者。 例如，您擁有兩個不同的 Microsoft 租使用者，而且您想要將電話號碼從一個租使用者移到另一個租使用者。  

  - **來源租使用者功能變數名稱** - 您想要將電話號碼移至其他租使用者的租使用者。  

  - **來源租使用者唯一識別碼** - 來源租使用者之租使用者識別碼。 這是一個選擇性欄位。  

  - **目的租使用者功能變數名稱** - 您想要將電話號碼移至的租使用者。  

  - **目的地租使用者唯一識別碼** - 目的地租使用者之租使用者識別碼。 這是一個選擇性欄位。  

  - **要求的日期時間*** - 您希望號碼從來源租使用者移至目的租使用者的日期與時間。 請參閱日期和時間。

  - **電話號碼清單** - 您想要從來源租使用者移至目標租使用者的電話號碼清單。 Upload包含電話號碼清單的 csv 檔案。 

- **庫存類型變更** ： 變更電話號碼 () 。 例如，您想要將 Microsoft 訂閱者號碼變更為服務號碼。 有關 Microsoft 支援的電話號碼類型詳細資訊，請參閱 [電話號碼類型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **轉換為** - 選取以將您的號碼轉換成使用者號碼或服務號碼。 

  - **偏好的日期時間*** - 您想要變更數位庫存類型的日期和時間。 請參閱日期和時間以瞭解更多資訊。

  - **核取方塊 -** 我瞭解，若要更新庫存類型，我的電話號碼必須取消指派 - Microsoft 無法處理電話號碼類型變更要求，除非您租使用者內的電話號碼未指派。 如果您要求未來日期進行此變更，則您必須在要求的日期與時間之前，確定號碼未分配。 

  - **電話號碼清單** - 您想要變更其類型的電話號碼清單。 Upload包含電話號碼清單的 csv 檔案。 

- **新的 TN 購買** – 從 Microsoft 購買新電話號碼。  

  - **數位類型** - 選取數位的類型。 請參閱 [電話號碼類型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **嘗試從系統管理** 中心入口Teams取得電話號碼 - 您是否嘗試從系統管理中心入口網站購買Microsoft Teams，您可以在這裡自助？  

  - **所需的電話號碼數量** - 這是要購買的電話號碼計數。  

  - **省/市** /市 / 省 - 您國家/地區內想要電話號碼的國家/省/市/ 省。  

  - **城市** - 您想要電話號碼的省/市/市。  

  - **Office** 位址 - 僅適用于特定國家/地區。 這是您辦公室的網站位址。  

  - **目錄清單** - 僅適用于特定國家/地區。 您想要使用電話號碼發佈公司資訊嗎？  

- **將現有** 電話號碼從目前的服務提供者移植到 Microsoft。  

  - **為埠訂單命名** - 提供易於記住的埠要求名稱。 

  -  **要求將日期/時間*** - 這是您想要將數位移植到 Microsoft 的日期和時間。 請注意，這不是有保證的移植日期，因為目前的號碼擁有者必須先核准我們的埠要求。 請參閱日期和時間。 

  - **埠號碼清單** - 這是要移植到 Microsoft 的電話號碼清單。 Upload包含電話號碼清單的 csv 檔案。 

  - **授權書 (LOA)** - 在這裡附加已簽署並填寫的 LOA。 沒有 LOA，Microsoft 就無法處理埠要求。  

- **位址更新** - 更新緊急電話位址。 請注意，此欄位僅適用于選取的國家/地區。 

  - **位置識別碼** - 緊急位址的位置識別碼。 

  - **電話號碼清單** - 您想要變更緊急位址的電話號碼清單， (描述欄位中輸入) 。 Upload包含電話號碼清單的 csv 檔案。 

***日期和時間。** 如果您選取 Country = France，date = 2021/8/14，time = 10am，則要求將于 2021 年 8 月 14 日上午 10 點執行。 法文時間。 

#### <a name="case-title"></a>大小寫標題

輸入摘要您的要求的標題。  

#### <a name="additional-contacts-for-notifications"></a>其他通知連絡人

輸入將會收到 Microsoft 自動狀態通知之人員清單。 例如，您想要將埠順序放在一起，而且除了您自己之外，還想要另外兩位同事接收自動狀態通知。 在通知電子郵件區段提供 **同事的電子郵件地址。** 這項資訊為選擇性。 

#### <a name="description"></a>描述

描述您嘗試達到的目標，並列出 Microsoft PSTN 服務台的問題。  

#### <a name="additional-supporting-documents"></a>其他支援檔

Upload案件的其他檔。  

## <a name="view-and-manage-existing-cases"></a>查看及管理現有案例

您可以選取查看我現有的案例，然後選取案例編號來查看您的案例。 選取案例編號會將您重新導向到案例詳細資料。  (您也可以選取查看公司案例來查看公司 **案例。)** 您也可以：

- **選取開啟案例**、所有案例或已結案 **案例** 來 **篩選您的案例**。

- **開啟現有案例** 、向下卷起，然後選取 [新增批註」，以與 PSTN 服務台溝通您的 **案例**。 新的視窗將會顯示。 在批註方塊中輸入您的訊息。 附加任何支援檔 (，) 可協助您提出要求，然後選取 **提交**。  

  來自 PSTN 服務台的回應會顯示在同一個時程表底下。 當案例有更新時，您會收到自動更新的自動電子郵件通知。 

- **流覽至現有** 案例、向下卷起，然後選取取消 **大小寫以取消案例。** 從下拉式清單中選取取消原因， **然後選取** 取消 。  

- **解決案例** - 如果您認為您的要求已經完成，您可以流覽至現有案例、向下卷起，然後選取解決 **大小寫來解決案例**。 選取 **關閉**;此案例現在會顯示為 已 **解決 – 問題已解決**。  


## <a name="related-topics-and-additional-resources"></a>相關主題和其他資源

- 如需與號碼設定和設定、授權、費用或帳單相關的協助，請參閱商務用產品支援連絡人 [- 系統管理協助](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。

- 有關您國家/地區可用的通話方案相關資訊，請參閱音訊會議與通話方案的國家/地區 [可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

- 有關可協助您選取組織 (類型) 電話號碼的資訊，請參閱不同類型的 [電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

- 有關管理貴組織電話號碼的資訊，請參閱 [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization.md)。

- 有關緊急通話條款與條件的資訊，請參閱 [緊急通話條款與條件](../emergency-calling-terms-and-conditions.md)。
