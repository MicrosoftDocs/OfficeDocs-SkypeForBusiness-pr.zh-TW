---
title: 將電話號碼移轉到 Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何使用移轉精靈，將您的電話號碼從目前的服務提供者移轉至 Microsoft Teams。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 98580a16f7d5165bef6bdd177de37a1e80bfb32f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790098"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>將電話號碼移轉到 Microsoft Teams

使用 Microsoft Teams 系統管理中心的移轉精靈，將電話號碼從您目前的服務提供者移轉到 Teams。 將電話號碼移轉到 Teams 之後，Microsoft 將會成為您的服務提供者，並會向您收取這些電話號碼。

開始之前，建議您檢閱 [移轉訂單中的資訊？](port-order-overview.md) 如果您有電話撥入式會議橋接器的服務號碼、自動語音應答或其他服務號碼、免付費電話號碼，或有超過 999 個使用者 (訂閱者) 需要移轉到 Teams 的電話號碼，請參閱 [管理組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 以下載正確的表單並將它們傳送給我們。

  > [!NOTE]
  > 我們處理移轉電話號碼的移轉訂單僅限美國個工作天，而非國定假日或週末。
  > 免付費電話號碼的移轉可用性可能會因國家/地區而異。 若要尋找我們的詳細資訊，請參閱您的國家或地區特定檔，以查看移轉服務的可用支援。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>建立移轉訂單並將電話號碼移轉到 Teams

> [!NOTE]
> **目前，您可以使用此精靈來取得英國、美國和加拿大的電話號碼**。 若要取得其他國家/地區的電話號碼，您可以 [手動提交移轉訂單](manually-submit-port-order.md)。 若要取得您需要手動提交移轉訂單的表單，請在 [ [管理組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] 下拉式清單中選取您的國家或地區。

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **[語音**  >  **電話號碼]**。 按一下 **[數位**]，然後按一下 [ **埠** ] 以啟動移轉精靈。
2. 檢閱 [ **開始** 使用] 頁面上的資訊，然後當您準備好時，按一下 [ **下一步]**。
3. 在 [ **選取位置和編號類型]** 頁面上，指定下列專案，然後按 [ **下一步]**：

    - **國家或地區**：您取得數位的國家或地區。
    - **電話號碼類型**：號碼類型，例如地理或免付費電話號碼。
    - **指派給** 的數位：指派給數位的物件。 例如，使用者、會議或語音功能。

4. 在 [ **新增帳戶資訊]** 頁面上，完成下列操作，然後按 [ **下一步]**。

    > [!IMPORTANT]
    > 此頁面上顯示的資訊是由國家或地區及編號類型決定。 每個國家和地區對移轉號碼所需的資訊有不同的規定。 您在此頁面上看到的內容可能與此處所述的內容不同。

    - **訂單詳細資料**： 
        - **訂單名稱**：訂單名稱
        - **通知電子郵件**：Email位址以接收訂單通知。 如果您輸入多個電子郵件地址，請以分號分隔每一個位址。
        - **移轉日期**：由您目前服務提供者發行的移轉日期。
    - **電話號碼詳細資料**
        - **埠類型**：無論您要執行完整移轉以移轉所有號碼，還是移轉部分埠以移轉部分號碼。
    - **要求詳細資料的人員**  
        - 您的組織名稱和要求移轉之人員的連絡人詳細資料。
    - **目前提供者的詳細資料**
        - **帳單電話號碼 (BTN)**：您的 BTN 為 E.164 格式，需要 + 符號才能加上號碼。 例如，若是北美洲數位，請使用 +1XXXYYZZ 格式。
        - 其他詳細資料，包括您目前服務提供者的名稱、您的帳戶號碼和服務位址。
            
5. 在 [ **新增號碼** ] 頁面上，按一下 **[選取檔案**]，流覽並選取包含您要傳輸之電話號碼的 CSV 檔案，然後按 [ **下一步]**。  

    > [!NOTE]
    > CSV 檔案必須只有一個名為 PhoneNumber 的標題列。 每個電話號碼都必須在另一列，而且只能是數位或 E.164 格式。

6. 在 [ **完成您的訂單** ] 頁面上，按一下 **[上傳簽署的授權書** ]，上傳已簽署之授權書的掃描複本 (LOA) 。

    如果您尚未下載並簽署 LOA，請執行下列動作：
    
    1. 按一下 [下載適用于您國家或地區的 LOA **] 範本** 。 
    2. 列印 LOA。
    3. 讓 LOA 由獲授權變更帳戶的人員簽署。
    4. 掃描簽署的 LOA，然後按一下 **[上傳已簽署的授權書** ] 來上傳。

    > [!NOTE]
    > 上傳 LOA 之後，提交您的訂單。 只上傳 LOA 就不夠了。 您也必須提交訂單，才能進行處理。

7. 檢閱您的訂單詳細資料，然後按一下 [ **提交]**。


## <a name="what-happens-next"></a>接下來會發生什麼事？

當我們收到您的移轉訂單時，您會收到一封電子郵件來驗證您的要求。 系統會每天檢查並更新您的要求，系統會在電子郵件中通知您的要求進度和狀態。 如果遺失電信業者拒絕您的移轉要求，請連絡 [TNS 服務台](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。

若要檢視移轉訂單的狀態，請在 Microsoft Teams 系統管理中心的左側導覽中，移至 [>**語音**  >  **埠訂單**]，然後按一下 [**訂購記錄]**。 每個移轉訂單狀態都會列在 **[狀態** ] 欄中。 若要深入瞭解，請參閱 [移轉訂單的狀態為何？](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>報告電話號碼問題？
如果您在埠完成後的前 24-48 小時內發現移轉號碼有任何問題，請連絡 [TNS 服務台](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)。 針對超過 48 小時的任何問題，請連絡Microsoft 支援服務小組。

## <a name="related-topics"></a>相關主題

- [什麼是移轉訂單？](port-order-overview.md)
- [通話方案所用的不同電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
