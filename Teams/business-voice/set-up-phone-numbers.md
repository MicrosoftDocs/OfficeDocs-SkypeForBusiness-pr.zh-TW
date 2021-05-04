---
title: 設定Microsoft 365 商務語音電話號碼
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何為貴Microsoft 365 商務語音使用者和服務設定電話號碼。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129996"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>步驟 2：設定商務語音電話號碼

在組織中設定使用者或自動助理之前，您必須取得他們的電話號碼。 有幾種不同類型的電話號碼，不過以下是您需要在此步驟中新增的兩種號碼類型：

- **服務編號** 這些號碼用於自動語音機、音訊會議和通話佇列。 它們可以是付費或免付費號碼，而且可以同時處理大量通話。 您的公司電話號碼必須成為服務號碼，因為稍後的步驟會指派給自動總機。
- **訂閱者號碼** 這些號碼會用於一般使用者，讓他們可以撥打和接聽電話。

> [!IMPORTANT]
> 即使您想要使用現有的電話號碼，您也需要建立暫時電話號碼，並指派給公司的主要電話線和使用者。 您可以在稍後的步驟中，以現有的電話號碼取代這些暫住號碼。

> [!NOTE]
> 您的新電話號碼可能需要數小時才能在 Teams。

## <a name="set-up-a-service-number"></a>設定服務號碼

您現在設定的服務號碼將在公司主要電話號碼的稍後步驟中使用。

1. 請前往 Microsoft Teams 系統管理中心。
2. 在左側流覽中，前往 **[語音** 電話  >  **數位，** 然後按一下 [**新增**。
3. 輸入訂單名稱並新增描述。
4. 在位置和數量頁面上，執行下列操作：
    1. 在 **國家/地區下**，選取國家/地區。
    2. 在 **數位類型** 下，選取下列其中一個選項：

        - **自動 (付費)** 一般、非免付費的電話號碼。 長途費用會向來電者收取。
        - **自動 (免付費)** 撥打美國和加拿大 (免費電話) 或免費電話 () 電話號碼。 長途費用會向貴公司收取。 在選取此選項之前，您必須購買通訊信用額度。 若要詳細資訊，請參閱我需要購買哪些產品，以[使用Microsoft 365 商務語音？](what-to-buy.md)。

    3. 在 **數量下**，選取 **1**。
        > [!NOTE]
        > 如果您收到 **訊息：您** 沒有足夠的授權要求更多這類號碼，請確定您購買的是 Business Voice 授權。 若要詳細資訊，請參閱我需要購買哪些產品，以[使用Microsoft 365 商務語音？](what-to-buy.md)。
    4. 在 **位置** 下，在設定緊急位置步驟中輸入您建立 [的位置](set-up-emergency-locations.md) 名稱。
    5. 在 **[區碼**） 下，選取區碼，然後按一下 **[下** 一步以選取您的號碼
5. 選取您想要的號碼。 您還有 10 分鐘的時間來選取電話號碼並下訂單。 如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。
6. 當您準備好要下單時，請按一下 [ **下單**，然後 **完成**

## <a name="set-up-phone-numbers-for-your-users"></a>設定使用者的電話號碼

1. 請前往 Microsoft Teams 系統管理中心。
2. 在左側流覽中，前往 **[語音** 電話  >  **數位，** 然後按一下 [**新增**。
3. 輸入訂單名稱並新增描述。
4. 在位置和數量頁面上，執行下列操作：

    1. 在 **國家/地區下**，選取國家/地區。
    2. 在 **數位類型** 下，選取 **使用者 (訂閱) 。**
    3. 在 **數量** 下，輸入貴組織想要的數位數目。
    4. 在 **位置下**，選取位置。 您可以選取在 [設定緊急位置> 步驟 [](set-up-emergency-locations.md)中新增的緊急位置，或者如果您需要為另一個辦公室或家用辦公室建立新位置，請按一下 [**新增位置**> 。
    5. 在 **[區碼**> 下，選取區碼，然後按一下 **[下** 一步> 以選取您的號碼。
5. 選取您想要的數位。 您還有 10 分鐘的時間來選取電話號碼並下訂單。 如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。
6. 當您準備好要下單時，請按一下 [ **下單**，然後 **完成**。

> [!div class="nextstepaction"]
> [下一個步驟：指派授權給Teams使用者](set-up-licenses.md)
