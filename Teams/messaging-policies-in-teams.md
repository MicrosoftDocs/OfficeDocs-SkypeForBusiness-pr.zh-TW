---
title: 管理 Teams 中的訊息傳遞原則
ms.author: mabond
author: mkbond007
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
description: 瞭解訊息中心原則，以及如何在 Teams 中用來控制聊天訊息。
ms.openlocfilehash: f74ae28176f147d768e8e551ac07d1bcf189836b
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563961"
---
# <a name="manage-messaging-policies-in-teams"></a>管理 Teams 中的訊息傳遞原則

<!--- Add zone marker here--->

訊息原則是用來控制哪些聊天和頻道訊息功能可供 [Microsoft Teams 中 (擁有者和成員) 的使用者 ](assign-roles-permissions.md) 使用。 您可以使用全組織 (預設) 自動建立的原則，或建立及指派自訂訊息原則。

除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。 編輯全域原則中的設定，或建立並指派一或多個自訂原則來開啟或關閉您要的功能。

> [!NOTE]
> 為了確保在原則變更之後進行同步處理，某些情況下可能需要重新開機。 

## <a name="create-a-custom-messaging-policy"></a>建立自訂訊息原則

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[訊息中心原則]**。
2. 選取 [新增 **]**。
3. 輸入原則的名稱和描述。
4. 選擇您想要的設定。
5. 選取 [儲存 **]**。

例如，您想要確認未刪除或變更已傳送的郵件。 建立名為「保留已傳送的郵件」的新自訂原則，並關閉下列設定：

- 擁有者可以刪除已傳送的郵件
- 使用者可以刪除已傳送的訊息
- 使用者可以編輯已傳送的訊息

然後將原則指派給使用者。

## <a name="edit-a-messaging-policy"></a>編輯訊息原則

您可以編輯全域原則和您建立的任何自訂原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[訊息中心原則]**。
2. 按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。
3. 從此處，進行您需要的變更。
4. 選取 [儲存 **]**。

## <a name="assign-a-custom-messaging-policy-to-users"></a>指派自訂訊息原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

使用者一次只能指派一個訊息原則。

> [!NOTE]
> 如果已將原則指派給使用者，就無法刪除該原則。 您必須先為所有受影響的使用者指派不同的原則，之後才可以刪除原始原則。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>訊息原則設定

以下是您可以設定的傳訊原則設定。

- **擁有者可以刪除已傳送的郵件**  使用此設定可讓擁有者刪除使用者傳送的頻道訊息或文章。
- **刪除已傳送的郵件** 使用此設定可讓使用者刪除在聊天中傳送的訊息。
- **刪除聊天** 使用此設定可讓使用者刪除在聊天中傳送的訊息。
- **編輯已傳送的郵件** 使用此設定可讓使用者編輯在聊天中傳送的訊息。
- **讀信回條** 讀信回條可讓聊天訊息的寄件者在 1：1 和群組聊天 20 人以下的情況下讀取訊息時收到通知。 郵件讀信回條會移除不確定是否已讀取郵件的相關資訊，並改善小組溝通。 電子檔探索報告中不會擷取讀信回條。  
    - **使用者控制** 這表示使用者可以決定是否要開啟或關閉讀信回條。 應用程式內的預設設定為 [開啟]。 使用者接著可以將它關閉。
    - **為所有人開啟** 這表示租使用者中的每個人都會開啟此功能，且沒有關閉此功能的選項。 針對 **所有人** 使用 [開啟] 設定時，為整個租使用者設定收據的唯一方法，是只針對整個租使用者設定一個訊息原則， (名為「全全組織 (組織預設) 」的預設原則) ，或是讓租使用者中的所有訊息原則都使用相同的收據設定。 當此功能對 [針對每個人開啟 **]** 啟用時，讀信回條功能最為有效。
    - **已針對所有人關閉** 這表示此功能已停用，且租使用者中沒有人有讀信回條，也無法將它開啟。
<a name="bkchat"> </a>

- **聊天**  如果您希望組織中的使用者能夠使用 Teams 應用程式與其他人聊天，請開啟此設定。
- *在交談中使用 Giphy** 如果您開啟 Giphy，使用者可以將 Giphy 包含在與其他人的聊天交談中。 Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。 每個 Giphy 都有內容分級。 除了開啟此設定之外，您還必須啟用 [選擇性連線體驗](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) ，才能在交談中使用 Giphy。
- **Giphy 內容分級**
  - **沒有限制** 這表示無論內容分級為何，您的使用者都可以在聊天中插入任何 Giphy。
  - **溫和**  這表示您的使用者將能夠在聊天中插入 Giphy，但成人內容會受到限制。
  - **嚴格**  這表示您的使用者將能夠在聊天中插入 Giphy，但成人內容會受到嚴格限制。
- **交談中的 Meme** 如果您開啟 [Memes]，使用者就可以在與其他人的聊天交談中包含 Meme。
- **交談中的圖戳** 如果您開啟此功能，使用者可以將貼圖包含在與其他人的聊天交談中。
- **URL 預覽** 使用此設定可開啟或關閉郵件中的自動 URL 預覽。
- **翻譯訊息** 開啟此設定，讓使用者自動將 Teams 訊息翻譯成其 Microsoft 365 或 Office 365 個人語言設定所指定的語言。
- **訊息的沈浸式閱讀程式** 開啟此設定可讓使用者檢視 Microsoft 沈浸式閱讀程式中的訊息。 沈浸式閱讀程式是一種學習工具，提供全螢幕閱讀體驗，提高文字的可讀性。
- **使用優先順序通知傳送緊急訊息** 如果您開啟此功能，使用者可以使用 [優先順序通知傳送訊息](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。 優先順序通知會每 2 分鐘通知使用者 20 分鐘，或直到收件者取回並讀取標示為 *緊急* 的郵件為止。 這項功能會提高及時處理郵件的可能性。 您無法在傳送郵件後編輯緊急訊息。
- **建立語音訊息**
  > [!Important]
  > 電子檔探索報告中不會擷取音訊訊息。
  - **在聊天和頻道中允許** 這表示使用者可以在聊天和頻道中留下音訊訊息。
  - **僅允許在聊天中使用** 這表示使用者可以在聊天中留下音訊訊息，但無法在頻道中留下。
  - **未啟用** 這表示使用者無法在聊天或頻道中建立音訊訊息。  
- **在行動裝置上，將最愛頻道顯示在最近的聊天上方** 啟用此設定可將最愛的頻道移到行動裝置畫面頂端，讓使用者不需要捲動來尋找。
- **從群組聊天移除使用者** 開啟此設定可讓使用者從群組聊天中移除其他使用者。 這項功能可讓您繼續與一小群人聊天，而不會遺失聊天記錄。
- **文字預測** 開啟此設定可讓使用者取得聊天訊息的文字預測。
- **建議的回復**  開啟此設定可為聊天訊息啟用建議的回復。
- **聊天許可權角色** 使用此設定來定義使用者受監督的聊天角色。 深入了解[監督的聊天](supervise-chats-edu.md)。
- **擁有完整聊天許可權的使用者可以刪除任何訊息** 使用此設定可讓具有完整許可權的使用者刪除任何群組或會議聊天訊息。

> [!NOTE]
> 其中有些設定，例如使用 Giphy，也可以由團隊擁有者在團隊層級，以及透過頻道擁有者在私人或共用頻道層級設定。

### <a name="related-topics"></a>相關主題

- [在 Teams 中指派原則給使用者和群組](assign-policies-users-and-groups.md)
- [在 Microsoft Teams 中指派 Teams 擁有者和成員](assign-roles-permissions.md)
