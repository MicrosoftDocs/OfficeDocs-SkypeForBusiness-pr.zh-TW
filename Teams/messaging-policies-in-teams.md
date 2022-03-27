---
title: 管理 Teams 中的訊息原則
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 瞭解傳訊政策，以及如何在聊天訊息中控制聊天Teams。
ms.openlocfilehash: 0f4001fc2a646b83f005d9cc48948fbbb314f042
ms.sourcegitcommit: 867e8b4120e81c93c029c0c1b9cb69c161fc87a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2022
ms.locfileid: "64480665"
---
# <a name="manage-messaging-policies-in-teams"></a>管理 Teams 中的訊息原則

<!--- Add zone marker here--->

訊息策略是用來控制哪些聊天和頻道訊息功能可供使用者 (擁有者和成員[) Microsoft Teams。](assign-roles-permissions.md) 您可以使用自動建立 (全組織的預設) ，或建立及指派自訂訊息策略。

除非您建立並指派自訂策略，否則貴組織中使用者會自動取得全域原則。 編輯全域原則中的設定，或建立並指派一或多個自訂策略來開啟或關閉您想要的功能。

> [!NOTE]
> 為了確保在策略變更後同步處理，可能需要重新開機特定實例。 

## <a name="create-a-custom-messaging-policy"></a>建立自訂訊息策略

1. 在系統管理中心的左側導Microsoft Teams，請前往 **訊息處理政策**。
2. 選取 [新增 **]**。
3. 輸入原則的名稱和描述。
4. 選擇您想要的設定。
5. 選取 [儲存 **]**。

例如，您想要確認未刪除或變更已送出的郵件。 建立名為「保留已寄郵件」的新自訂策略，並關閉下列設定：

- 擁有者可以刪除已送出的郵件
- 使用者可以刪除已送出的郵件
- 使用者可以編輯已送出的郵件

然後將該策略指派給使用者。

## <a name="edit-a-messaging-policy"></a>編輯訊息策略

您可以編輯全域原則和您建立的任何自訂原則。

1. 在系統管理中心的左側導Microsoft Teams，請前往 **訊息處理政策**。
2. 按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。
3. 從此處，進行您需要的變更。
4. 選取 [儲存 **]**。

## <a name="assign-a-custom-messaging-policy-to-users"></a>指派自訂訊息策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

一次只能指派一個訊息策略給使用者。

> [!NOTE]
> 如果已將原則指派給使用者，就無法刪除該原則。 您必須先為所有受影響的使用者指派不同的原則，之後才可以刪除原始原則。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>訊息策略設定

以下是您可以設定的訊息原則設定。

- **擁有者可以刪除已送出的郵件**  使用此設定，讓擁有者刪除使用者所寄的頻道訊息或文章。
- **刪除已送出的郵件** 使用此設定可讓使用者刪除他們在聊天中送出的郵件。
- **編輯已送出的郵件** 使用此設定可讓使用者編輯他們在聊天中送出的郵件。
- **已讀回條** 讀取回條允許當收件者以 1：1 讀取其訊息，以及群組聊天 20 人以下時，通知聊天訊息的寄件者。 郵件讀信回條會不確定地移除郵件是否已讀取，並改善小組溝通。 電子資料探索報告不會捕獲已讀回條。  
    - **使用者控制** 這表示使用者可以決定是否要讀取回條為 ON 或 OFF。 應用程式中的預設設定為 ON。 使用者接著可以將其關閉。
    - **已針對所有人開啟** 這表示租使用者中的每個人都會擁有開啟功能，沒有關閉功能的選項。 使用適用于所有人的 On 設定時，為整個租使用者設定回條的唯一方法，就是為整個租使用者設定一個訊息策略 (稱為「全域 (全組織預設) 」) ，或是讓租使用者中所有的訊息策略都使用相同的接收設定。 當此功能對 [針對每個人開啟 **]** 啟用時，讀信回條功能最為有效。
    - **已針對所有人關閉** 這表示此功能已停用，而且租使用者中沒有人已讀取回條，也無法開啟。
<a name="bkchat"> </a>

- **聊天** 如果您希望貴組織的使用者能夠使用 Teams應用程式與其他人員聊天，請開啟此設定。
- *在交談中使用 Giphy** 如果您開啟 Giphys，使用者可以在與他人的聊天交談中納入 Giphys。 Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。 每個 Giphy 都有內容分級。 除了開啟此設定之外，您還需要啟用選擇性連線 [體驗](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) ，才能在交談中允許 Giphys。
- **Giphy 內容分級**
  - **沒有限制** 這表示無論內容分級如何，您的使用者都能在聊天中插入任何 Giphy。
  - **溫和**  這表示您的使用者將能夠在聊天中插入 Giphys，但會受到成人內容的中等限制。
  - **嚴格**  這表示您的使用者將能夠在聊天中插入 Giphys，但會嚴格限制成人內容。
- **交談中的 Meme** 如果您開啟 Memes，使用者可以在與他人的聊天交談中納入 Memes。
- **交談中的貼圖** 如果您開啟此選項，使用者可以在與他人的聊天交談中納入貼圖。
- **URL 預覽** 使用此設定可開啟或關閉郵件中的自動 URL 預覽。
- **翻譯郵件** 開啟此設定，讓使用者自動將Teams訊息翻譯成其個人語言設定所指定的語言，Microsoft 365或Office 365。
- **郵件的沉浸式閱讀程式** 開啟此設定，讓使用者在 Microsoft 沈浸式閱讀程式。 沈浸式閱讀程式是一種學習工具，可提供全螢幕閱讀體驗，提高文字的可讀性。
- **使用優先順序通知傳送緊急郵件** 如果您開啟此選項，使用者可以使用優先順序通知 [傳送郵件](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。 優先順序通知會每隔 2 分鐘通知使用者 20 分鐘，或直到收件者選取並讀取標示為緊急的郵件。 此功能會增加郵件及時處理的可能性。
- **建立語音留言**
  > [!Important]
  > eDiscovery 報表不會捕獲音訊訊息。
  - **在聊天和頻道中允許** 這表示使用者可以在聊天和頻道中留下音訊訊息。
  - **僅允許在聊天中** 這表示使用者可以在聊天中保留音訊訊息，但不能在頻道中留言。
  - **未啟用** 這表示使用者無法在聊天或頻道中建立音訊訊息。  
- **在行動裝置上，顯示最近聊天上方的最愛頻道** 啟用此設定，將最愛的頻道移至行動裝置畫面的頂端，讓使用者不需要捲動來尋找。
- **從群組聊天移除使用者** 開啟此設定，讓使用者從群組聊天移除其他使用者。 這項功能可讓您繼續與一小群人員聊天，而不會失去聊天記錄。
- **文字預測** 開啟此設定，讓使用者取得聊天訊息的文字預測。
- **建議的回復**  開啟此設定以啟用聊天訊息的建議回復。
- **聊天許可權角色** 使用此設定可定義使用者的監督聊天角色。 深入了解[監督的聊天](supervise-chats-edu.md)。
- **擁有完整聊天許可權的使用者可以刪除任何訊息** 使用此設定可讓使用者擁有完整許可權的使用者刪除任何群組或會議聊天訊息。

> [!NOTE]
> 其中一些設定 ，例如使用 Giphys，也可以由團隊擁有者在團隊層級設定，以及頻道擁有者在私人或共用頻道層級設定。

### <a name="related-topics"></a>相關主題

- [為使用者和群組指派Teams](assign-policies-users-and-groups.md)
- [在 Microsoft Teams 中指派 Teams 擁有者和成員](assign-roles-permissions.md)
