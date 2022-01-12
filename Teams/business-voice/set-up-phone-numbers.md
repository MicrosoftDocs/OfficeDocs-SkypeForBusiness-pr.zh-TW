---
title: 使用Microsoft 365 Teams 電話通話方案設定通話方案
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何使用貴Microsoft 365 Teams 電話使用者與服務的通話方案電話號碼來設定通話方案號碼。
appliesto:
- Microsoft Teams
ms.openlocfilehash: eefdfcb764f44830bb6dc23c63c2a80701c32c3e
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766616"
---
# <a name="step-2-set-up-teams-phone-phone-numbers"></a>步驟 2：設定Teams 電話電話號碼

在組織中設定使用者或自動助理之前，您必須取得他們的電話號碼。 有幾種不同類型的電話號碼，不過以下是您需要在此步驟中新增的兩種號碼類型：

- **服務編號** 這些號碼用於自動語音機、音訊會議和通話佇列。 它們可以是付費或免付費號碼，而且可以同時處理大量通話。 您的公司電話號碼必須成為服務號碼，因為稍後的步驟會指派給自動總機。
- **訂閱者號碼** 這些號碼會用於一般使用者，讓他們可以撥打和接聽電話。

> [!IMPORTANT]
> 即使您想要使用現有的電話號碼，您也需要建立暫時電話號碼，並指派給公司的主要電話線和使用者。 您可以在稍後的步驟中，以現有的電話號碼取代這些暫住號碼。

> [!NOTE]
> 您的新電話號碼可能需要數小時才能在 Teams。

## <a name="set-up-a-service-number"></a>設定服務號碼

您現在設定的服務號碼將在公司主要電話號碼的稍後步驟中使用。

1. 開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (通常是您用來註冊帳戶Microsoft 365) 。
2. 在左側流覽中，前往 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**[語音** 電話  >  **數位**</a>，然後按一下 [**新增**。
3. 輸入訂單名稱並新增描述。
4. 在位置和數量頁面上，執行下列操作：
    1. 在 **國家/地區下**，選取國家/地區。
    2. 在 **數位類型** 下，選取下列其中一個選項：

        - **自動 (付費)** 一般、非免付費的電話號碼。 長途費用會向來電者收取。
        - **自動 (免付費)** 撥打美國和加拿大 (免費電話) 或免費電話 () 電話號碼。 長途費用會向貴公司收取。 在選取此選項之前，您必須購買通訊信用額度。 若要取得詳細資訊，請參閱我需要購買哪些產品，才能取得中小型企業的語音[功能？。](whats-business-voice.md)

    3. 在 **數量下**，選取 **1**。
        > [!NOTE]
        > 如果您收到 **訊息：您** 沒有足夠的授權要求更多這類號碼，請確定您Teams 電話通話方案授權。 若要取得詳細資訊，請參閱我需要購買哪些產品，才能取得中小型企業的語音[功能？。](whats-business-voice.md)
    4. 選擇位置 **或** 區碼 **，取決於您** 是想要使用位置的城市搜尋電話號碼，還是想要搜尋特定區碼中的號碼。
    5. 如果您 **選取位置**：

        1. 輸入緊急位址位於 [設定緊急位置位置> 步驟 [](set-up-emergency-locations.md)中的城市，或如果您需要為另一個辦公室或家用辦公室建立新位置，請按一下 [**新增位置**> 。
        2. 在 **區碼下**，選取區碼， **然後選取下** 一步以保留您的號碼。

    6. 如果您選取區 **碼，** 輸入要搜尋的區碼，然後 **選取下一** 步以保留您的號碼。

5. 選取您想要的號碼。 您還有 10 分鐘的時間來選取電話號碼並下訂單。 如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。
6. 當您準備好要下單時，請按一下 [ **下單**，然後 **完成**

## <a name="set-up-phone-numbers-for-your-users"></a>設定使用者的電話號碼

1. 開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員的使用者登入。這通常是您用來註冊帳戶Microsoft 365。
2. 在左側流覽中，前往 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**[語音** 電話  >  **數位**</a>，然後按一下 [**新增**。
3. 輸入訂單名稱並新增描述。
4. 在位置和數量頁面上，執行下列操作：

    1. 在 **國家/地區下**，選取國家/地區。
    2. 在 **數位類型** 下，選取 **使用者 (訂閱) 。**
    3. 在 **數量** 下，輸入貴組織想要的數位數目。
    4. 選擇位置 **或** 區碼 **，取決於您** 是想要使用位置的城市搜尋電話號碼，還是想要搜尋特定區碼中的號碼。
    5. 如果您 **選取位置**：

        1. 輸入緊急位址位於 [設定緊急位置位置> 步驟 [](set-up-emergency-locations.md)中的城市，或如果您需要為另一個辦公室或家用辦公室建立新位置，請按一下 [**新增位置**> 。
        2. 在 **區碼下**，選取區碼， **然後選取下** 一步以保留您的號碼。

    6. 如果您選取區 **碼，** 輸入要搜尋的區碼，然後 **選取下一** 步以保留您的號碼。
5. 選取您想要的數位。 您還有 10 分鐘的時間來選取電話號碼並下訂單。 如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。
6. 當您準備好要下單時，請按一下 [ **下單**，然後 **完成**。

> [!div class="nextstepaction"]
> [下一個步驟：指派授權給Teams使用者](set-up-licenses.md)
