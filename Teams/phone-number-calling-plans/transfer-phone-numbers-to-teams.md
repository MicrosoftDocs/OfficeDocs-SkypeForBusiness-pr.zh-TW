---
title: 將電話號碼移轉至 Microsoft Teams
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
description: 瞭解如何使用移轉精靈將您目前服務提供者的電話號碼移轉至 Microsoft Teams。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dfc3141eea8d16a86c0f37221e597feac3bb957e
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421278"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>將電話號碼移轉至 Microsoft Teams

使用 Microsoft Teams 系統管理中心的移轉精靈，將您目前服務提供者的電話號碼移轉至 Teams。 將電話號碼埠至 Teams 之後，Microsoft 將會成為您的服務提供者，並針對這些電話號碼向您計費。

在開始之前，我們建議您先查看什麼是埠 [訂單的資訊？](port-order-overview.md) 如果您有電話撥入式會議橋接器的服務號碼、自動語音機或其他服務號碼、免付費電話號碼，或擁有超過 999 個使用者 (訂閱者) 電話號碼，您需要轉接至 Teams，請參閱管理貴組織的電話號碼，以下載正確的[](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)表單並傳送給我們。

  > [!NOTE]
  > 我們只會處理移轉電話號碼的移轉訂單，而非假日或週末。

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>建立移轉訂單，並移轉電話號碼至 Teams

> [!NOTE]
> **目前，您可以使用此精靈取得英國、美國和加拿大的電話號碼**。 若要取得其他國家/地區的電話號碼，您可以手動 [提交埠訂單](manually-submit-port-order.md)。 若要取得您需要手動提交埠訂單的表單，請在管理您組織的電話號碼下拉式清單中，選取 [您的國家/地區](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **電話號碼**。 按一下 **[數位**，然後按一下 **埠** 以啟動埠精靈。
2. 請于 [開始入門 **」** 頁面上查看資訊，然後在準備就緒時按一下 [下 **一步**。
3. 在 [ **選取位置和數位類型** 頁面， 指定下列專案，然後按一下 [下 **一步**：

    - **國家/地區**：您收到號碼的一或區域。
    - **電話號碼類型**：號碼類型，例如地理號碼或免付費電話號碼。
    - **指派給的數位**：指派給哪些數位。 例如，使用者、會議或語音功能。

4. 在 [ **新增帳戶資訊** 」 頁面上，完成下列步驟，然後按一下 [下 **一步**。

    > [!IMPORTANT]
    > 此頁面上顯示的資訊取決於國家/地區或數位類型。 每個國家/地區對埠號碼所需資訊有不同的法規。 您在此頁面上看到的內容可能會與本文所述不同。

    - **訂單詳細資料**： 
        - **訂單名稱**：您的訂單名稱
        - **通知電子郵件**：接收訂單通知的電子郵件地址。 如果您輸入多個電子郵件地址，請以分號分隔每個電子郵件地址。
        - **移轉日期**：由您目前的服務提供者所發行的移轉日期。
    - **電話號碼詳細資料**
        - **埠類型**：無論是執行完整埠來傳輸所有號碼，還是部分移轉部分號碼。
    - **要求詳細資料的人**  
        - 貴組織的名稱及要求移轉之人員之連絡人詳細資料。
    - **目前提供者的詳細資訊**
        - **計費電話號碼 (BTN) ：** 您的 BTN 格式為 E.164，需要 + 符號，以在號碼前。 例如，針對北美號碼，請使用 +1XXXYYYZZZZ 格式。
        - 其他詳細資料，包括您目前的服務提供者名稱、您的帳戶號碼，以及您的服務位址。
            
5. 在 [**新增號碼」** 頁面上，按一下 [選取檔案，流覽至並選取包含要傳輸的電話號碼的 CSV 檔案，然後按一下 [下 **一步**。  

    > [!NOTE]
    > CSV 檔案只能有一個標題為 PhoneNumber 的資料行。 每個電話號碼必須位於另一列，而且只能是數位或 E.164 格式。

6. 在 [**完成您的訂單>** 頁面上，按一下 [上傳已簽署的授權書，以上傳已簽署授權書的掃描 (LOA) 。

    如果您尚未下載並簽署 LOA，請執行下列操作：
    
    1. 按一下 **[下載範本** ， 以下載您國家/地區或地區的 LOA。 
    2. 列印 LOA。
    3. 由獲授權變更帳戶的人員簽署 LOA。
    4. 掃描簽署的 LOA，然後按一下 **[上傳已簽署的** 授權書以上傳授權書。

    > [!NOTE]
    > 上傳 LOA 之後，提交您的訂單。 只上傳 LOA 並不夠。 您還必須提交訂單，才能處理訂單。

7. 請閱閱您的訂單詳細資料，然後按一下 **[提交**。


## <a name="what-happens-next"></a>接下來會發生什麼情況？

當我們收到您的埠訂單時，您會收到一封驗證您要求的電子郵件。 您的要求會每天檢查和更新，且會以電子郵件通知您其進度和狀態。 如果失敗電信公司拒絕您的埠要求，請連上 [PSTN 服務台](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

若要查看您的埠訂單狀態，請在 Microsoft Teams 系統管理中心的左側流覽中，>**語音** 埠訂單，然後按一下 [訂單  >  ******記錄**。 每個埠訂單狀態會列在狀態 **欄中** 。 若要深入瞭解，請參閱 [您的埠訂單狀態如何？](port-order-status.md)

## <a name="related-topics"></a>相關主題

- [什麼是移轉訂單？](port-order-overview.md)
- [用於通話方案的電話號碼類型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
