---
title: 迴圈元件概觀Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Teams 中管理迴圈Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 660ecd7542eadd56b284642895e5da15a1cdd434
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918937"
---
# <a name="overview-of-loop-components-in-teams"></a>迴圈元件概觀Teams

在聊天中Teams元件，提供一種共同構思、建立及做出決策的新方式。 傳送元件 ，例如表格、工作清單或段落，讓聊天中的每個人都能在線上編輯，並查看變更。 

> [!Note]
> 迴圈元件是[Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop)應用程式的第一項功能，可在 Teams。 

**一起更快速地完成工作。** 群組來源議程、追蹤群組的動作專案，或共同記錄筆記。 這些只是讓迴圈元件更容易的一些案例。

**共用元件。** 在這個版本中，您可以將迴圈元件共用至不同的Teams聊天。 收件者無論身在何處都可以編輯，而且無論變更在何處，都可以立即看到更新。

**從聊天開始，從該開始建立。** 您從聊天Teams建立的每一個元件都會自動儲存到 OneDrive。 因此，您可能會開始在聊天中共同合作，然後再移至檔案，因為檔案的視覺空間較大，可以視需要新增更多元件。

有關迴圈元件在 Teams 中的系統管理設定，請參閱[管理](/sharepoint/manage-loop-components)SharePoint。

## <a name="clients-and-platforms"></a>用戶端和平臺

適用于 Teams、Mac Windows Linux、iOS 和 Android 上的應用程式。

## <a name="loop-components-and-fluid-files"></a>迴圈元件和 .fluid 檔案

迴圈元件Teams由儲存在建立者檔案中的 .fluid 檔案OneDrive。 成為檔案OneDrive表示使用者可以建立、探索及管理迴圈元件 (.流暢) ，就像任何Office一樣。 .fluid 檔案可處理電子檔探索、稽核、報告和法律保留等資料監管功能。

## <a name="how-are-fluid--files-stored"></a>如何儲存 .fluid 檔案？

.fluid 檔案會顯示在 Office.com 和 OneDrive，例如位於最近和建議的區域。 使用者可以從 Office.com 和 OneDrive 搜尋 .fluid 檔案中OneDrive。 .fluid 檔案可以從 OneDrive 還原到OneDrive。 若要建立迴圈元件聊天參與者必須擁有OneDrive帳戶。 如果沒有有效的OneDrive帳戶，聊天參與者仍可在其他使用者所建立的元件上共同OneDrive帳戶，但無法建立自己的元件。 

將 .fluid 檔案從 OneDrive移動到SharePoint網站會導致即時元件無法載入至Teams聊天。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果檔案擁有者離開公司，會發生什麼情況？

OneDrive保留原則適用于 .fluid 檔案，就像適用于使用者建立的其他內容一樣。

## <a name="how-are-fluid-files-shared"></a>如何共用 .fluid 檔案？

迴圈元件可以在聊天中插入Teams，或從一個聊天複製到另一個聊天。  (通道中尚不支援迴圈元件。) 它們預設為組織的現有許可權，但使用者可以在傳送前變更許可權，以確保每個人都能存取。

在 Teams.com 中開啟Office聊天的元件，提供視窗頂端的共用功能，類似其他檔Office選項。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 檔案損毀或損毀，該怎麼處理？

版本歷程記錄可讓您從檔案的先前版本進行審閱和複製。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些應用程式可以開啟和編輯 .fluid 檔案？

.fluid 檔案只能在瀏覽器中以連結開啟，例如 Office.com，以及聊天中的迴圈Teams元件。 下載後，若未先將檔上傳回OneDrive或SharePoint。

## <a name="known-issues"></a>已知問題

- 在 Android 上使用聊天時，無法透過Office 應用程式編輯聊天Teams元件。
- 如果租使用者的預設檔案許可權設定為 [特定人員 (只有使用者指定的人員) ，而寄件者在建立元件時，會從許可權對話方塊中的 [特定人員清單上移除部分使用者」，這些使用者可能仍具有內容存取權。
- 將租使用者預設檔案許可權設定為 [特定人員 (只有使用者指定的人員) ，將連結複製到即時元件，並在另一個聊天中進行粘貼，則寄件者需要使用許可權對話方塊，並新增 [特定人員選項中收件者以正確授予存取權。
- 將租使用者預設檔案許可權設定為特定 *人員 (只有* 使用者指定的人員) ，在超過 20 個成員的群組聊天中建立即時元件，會要求寄件者手動選取元件的許可權選項。
- 在搜尋中搜尋迴圈Teams會返回連結至 office.com 中的元件，而不是聊天訊息本身。
- 在聯合聊天中，迴圈元件會停用。
- B2B 來賓將無法透過公司共用連結，在即時元件上共同合作。 將許可權設定為 **目前在此聊天中的人員** ，以與 B2B 來賓共用元件。
- 在頻道中不支援Teams元件。
- 只有在檔案移至不同的文件庫時，才能載入聊天中的迴圈元件。 如果檔案移至不同的資料夾，檔案會繼續在聊天中載入。
