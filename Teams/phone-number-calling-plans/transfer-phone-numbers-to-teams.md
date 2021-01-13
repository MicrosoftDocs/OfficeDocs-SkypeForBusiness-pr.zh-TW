---
title: 將電話號碼轉移至 Microsoft 團隊
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 [移植] 嚮導，將您的電話號碼從目前的服務提供者轉接到 Microsoft 團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52dd8a2a1dcbc14930695efd52141ce3b1842458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812963"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>將電話號碼轉移至 Microsoft 團隊

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

使用 Microsoft 團隊系統管理中心中的移植嚮導，將您的電話號碼從目前的服務提供者轉移至團隊。 在您將電話號碼移植至團隊後，Microsoft 就會成為您的服務提供者，並將您的電話號碼帳單。

在開始之前，我們建議您查看[埠順序](port-order-overview.md)中的資訊。 如果您有電話撥入式會議橋接、自動語音應答或其他服務號碼、免付費電話號碼，或超過999個使用者 (訂閱者，請) 要傳送給團隊的電話號碼，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 以下載正確的表單，並傳送給我們。

  > [!NOTE]
  > 我們處理的埠訂單只會在美國營業日傳送電話號碼，而不是在公用假日或週末進行。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>建立埠順序並將您的電話號碼轉接至團隊

> [!NOTE]
> **目前，您可以使用此嚮導來取得英國、美國和加拿大的電話號碼**。 若要取得其他國家和地區的電話號碼，您可以 [手動提交埠順序](manually-submit-port-order.md)。 若要取得手動提交埠順序所需的表單，請在 [ [管理您的組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] 下拉式清單中，選取您的國家或地區。

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **電話號碼**]。 按一下 [ **數位**]，然後按一下 [ **埠** ] 以啟動移植嚮導。
2. 查看 [ **入門** ] 頁面上的資訊，然後在您準備好時，按一下 **[下一步]**。
3. 在 [ **選取位置與編號類型** ] 頁面上，指定下列內容，然後按 **[下一步]**：

    - [**國家/地區**]：您要取得數位的國家或地區。
    - **電話號碼類型**：號碼類型，例如地理或免付費電話號碼。
    - **指派** 給您的數位：號碼的分派物件。 例如，使用者或會議或語音功能。

4. 在 [ **新增帳戶資訊** ] 頁面上，完成下列動作，然後按一下 **[下一步]**。

    > [!IMPORTANT]
    > 此頁面上顯示的資訊是由國家或地區和數位類型決定。 每個國家和地區對埠號碼所需的資訊都有不同的管理法規。 您在此頁面上看到的內容可能與此處所述的不同。

    - **訂單詳細資料**： 
        - **訂單名稱**：您的訂單名稱
        - **通知電子** 郵件：接收訂單通知的電子郵件地址。 如果您輸入多個電子郵件地址，請以分號分隔每個位址。
        - 已 **轉移日期**：您目前服務提供者所簽發的轉移日期。
    - **電話號碼詳細資料**
        - **埠類型**：不論您要執行的是全埠，都要傳送您的所有號碼或部分埠來傳送部分號碼。
    - **人員要求詳細資料**  
        - 您的組織名稱和要求轉移之人員的連絡人詳細資料。
    - **目前提供者的詳細資料**
        - **帳單電話號碼 (BTN)**：您的 BTN 格式為 e.i 格式，需要 + 號才能預先加上數位。 例如，對於北美電話，請使用 + 1XXXYYYZZZZ 格式。
        - 其他詳細資料，包括您目前服務提供者的名稱、您的帳戶號碼和您的服務位址。
            
5. 在 [ **新增號碼** ] 頁面上，按一下 [ **選取** 檔案]，流覽至並選取包含您要轉移之電話號碼的 CSV 檔案，然後按一下 **[下一步]**。  

    > [!NOTE]
    > CSV 檔案必須只有一個名為 PhoneNumber 的資料行。 每個電話號碼必須在不同的列上，且只能是數位或164格式。

6. 在 [ **完成您的訂單** ] 頁面上，按一下 **[上傳已簽署的授權** ]，以上傳已簽署的授權 (LOA) 的已掃描複本。

    如果您尚未下載並簽署 LOA，請執行下列動作：
    
    1. 按一下 [ **下載範本** ]，下載您國家或地區的 LOA。 
    2. 列印 LOA。
    3. 請由獲授權變更帳戶的人員簽署 LOA。
    4. 掃描已簽署的 LOA，然後按一下 **[上傳已簽署的授權** ] 進行上傳。

    > [!NOTE]
    > 上傳您的 LOA 之後，請提交您的訂單。 只要上傳 LOA 就夠了。 您也必須提交訂單以進行處理。

7. 查看您的訂單詳細資料，然後按一下 [ **提交**]。


## <a name="what-happens-next"></a>接下來會發生什麼事？

當我們收到您的埠順序時，您會收到一封確認您要求的電子郵件。 每日都會檢查並更新您的要求，您會在電子郵件中收到其進度和狀態的通知。 如果您的埠要求遭到遺失的載體拒絕，請與 [PSTN 服務服務台](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)聯繫。

若要查看您的埠順序狀態，請在 Microsoft 團隊系統管理中心的左導覽中，移至 > 的 **語音**  >  **埠訂單**，然後按一下 [**訂單歷程記錄**]。 每個埠訂單狀態都列在 [ **狀態** ] 欄中。 若要深入瞭解，請參閱 [您的埠訂單狀態為何？](port-order-status.md)

## <a name="related-topics"></a>相關主題

- [什麼是移轉訂單？](port-order-overview.md)
- [通話方案所用的不同類型的電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
