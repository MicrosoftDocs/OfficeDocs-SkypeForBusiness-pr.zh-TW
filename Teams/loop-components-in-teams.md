---
title: Teams 中的迴圈元件概觀
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
description: 瞭解如何在 Teams 中管理迴圈元件。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e0b9c5a7ffef07a1d9245d2b1266a071b4ee0c2
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795052"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams 中的迴圈元件概觀

Teams 聊天中的迴圈元件提供一種新的方式，讓您一起構想、建立和做出決策。 傳送元件，例如表格、工作清單或段落，讓聊天中的每個人都可以進行內嵌編輯，並在變更時看到變更。 

> [!Note]
> 迴圈元件是 Teams 中提供[Microsoft Loop應用程式](https://www.microsoft.com/en-us/microsoft-loop)的第一項功能。 

**共同完成工作更快。** 群組議程、追蹤群組的動作專案，或共同記錄筆記。 這些只是幾個使用迴圈元件更輕鬆的案例。

**共用元件。** 在此版本中，您可以在不同的 Teams 聊天中共用迴圈元件。 收件者可以隨時隨地進行編輯，而且無論在何處進行變更，都能立即查看更新。

**從聊天開始，從該處建立。** 您從 Teams 聊天建立的每個元件都會自動儲存到 OneDrive 中的檔案。 因此，您可能會在聊天中開始共同作業，之後移至 Office.com 上的檔案，您可以在其中有更大的視覺空間進行編輯，並可視需要新增任意數量的元件。

如需 Teams 中迴圈元件系統管理設定的相關資訊，請參閱 [在 SharePoint 中管理迴圈元件](/sharepoint/manage-loop-components)。

## <a name="clients-and-platforms"></a>用戶端和平臺

適用于 Windows、Mac、Linux、iOS 和 Android 上的 Teams 應用程式。

## <a name="loop-components-and-fluid-files"></a>迴圈處理元件和 .fluid 檔案

在 Teams 中建立的迴圈元件是由 .fluid (所支援，近期內儲存在建立者 OneDrive 中的) 檔案將會變更為 .loop。 OneDrive 中的檔案表示使用者可以像任何 Office 檔一樣輕鬆地建立、探索和管理 Loop 元件 (.fluid 檔案) 。 

## <a name="how-are-fluid-files-stored"></a>如何儲存 .fluid 檔案？

.fluid 檔案會顯示在 Office.com 和 OneDrive 上，例如 [最近] 和 [建議] 區域。 使用者可以從 Office.com 和 OneDrive 搜尋 .fluid 檔案中的內容。 .fluid files can be restored to previous versions from OneDrive. 若要建立迴圈元件，聊天參與者必須擁有 OneDrive 帳戶。 如果沒有有效的 OneDrive 帳戶，聊天參與者可能仍然可以針對擁有有效 OneDrive 帳戶但無法建立自己的元件的其他使用者所建立的元件進行共同作業。 

將 .fluid 檔案從 OneDrive 移至 SharePoint 網站會導致即時元件無法在 Teams 聊天中載入。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果檔案擁有者離開公司，會發生什麼情況？

OneDrive 保留原則會套用至 .fluid 檔案，就像套用到使用者建立的其他內容一樣。

## <a name="how-are-fluid-files-shared"></a>如何共用 .fluid 檔案？

迴圈元件可以插入 Teams 聊天或從一個聊天複製到另一個聊天。  (通道尚未支援迴圈元件。) 它們預設為組織現有的許可權，但使用者可以在傳送前變更許可權，以確保每個人都能存取。

在 Office.com 中從 Teams 聊天開啟元件可在視窗頂端提供共用功能，類似其他 Office 檔提供的共用選項。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 檔案損毀或損壞該怎麼辦？

版本歷程記錄可讓您檢閱、還原或複製舊版檔案。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些應用程式可以開啟和編輯 .fluid 檔案？

.fluid 檔案只能在瀏覽器中開啟為連結，例如 Office.com，以及 Teams 聊天中的迴圈元件。 如果已下載，則必須先將它們上傳到 OneDrive 或 SharePoint，就無法再次開啟。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid 檔案是否支援 eDiscovery？

.fluid 檔案可被搜尋，但電子檔探索工作流程支援有限。 目前，.fluid 檔案會儲存在建立者的 OneDrive 中，而且可以在 eDiscovery (Standard) 和 eDiscovery (Premium) 中搜尋和收集。 不過，它們不會在預覽中呈現，而且現有工具無法耗用檢閱的匯出格式。 若要檢視匯出的內容，請將它們上傳到任何 OneDrive。 如有需要，您可以暫時停用這些體驗，如 [ [設定管理](/sharepoint/manage-loop-components#settings-management) ] 區段中所述。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>如果從系統管理切換停用 Loop，使用者體驗會是什麼？

如果您停用 [ [設定管理](/sharepoint/manage-loop-components#settings-management) ] 區段中所述的這些體驗，將會套用下列體驗變更：

- Teams 訊息中的建立/插入進入點將會隱藏。 使用者將無法建立新的 .fluid 檔案。
- 先前已呈現為互動式 Loop 元件的現有郵件，會改為轉譯為超連結「迴圈元件」。 Teams 中不會顯示任何互動式內容。
- 當使用者按一下 [迴圈元件] 超連結，或流覽至 商務用 OneDrive 中的 .fluid 檔案並按一下以開啟時，該檔案會在另一個瀏覽器索引標籤中開啟。使用者仍然可以編輯檔案。

## <a name="known-issues"></a>已知的問題

- 如果將租使用者預設檔案許可權設定為 *[特定人員* ]， (使用者指定) 的人員，請將連結複製到 [迴圈] 元件並貼到其他聊天中，則寄件者必須使用許可權對話方塊，並在 [特定人員] 選項中新增收件者，才能正確授與存取權。
- 在租使用者預設檔案許可權設定為 [ *特定人員* ] (使用者指定的人員) ，在與超過 20 位成員的群組聊天中建立即時元件，將需要寄件者手動選取元件的許可權選項。
- 在 Teams 搜尋中搜尋迴圈元件時，會傳回 office.com 元件的連結，而不是聊天訊息本身。
- 同盟聊天會停用迴圈元件。
- 來賓無法針對透過公司共用連結與其共用的即時元件進行共同作業。 設定 **目前在此聊天中人員** 許可權，以與來賓共用元件。
- Teams 頻道不支援迴圈元件。
- 只有當檔案移至不同的文件庫時，聊天中的迴圈元件才會載入。 如果檔案移到不同的資料夾，則檔案會繼續載入在聊天中。
