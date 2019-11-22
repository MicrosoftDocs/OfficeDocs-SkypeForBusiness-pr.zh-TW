---
title: Microsoft 團隊中的保留原則
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 瞭解如何保留原則，以及如何在團隊中管理它們。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793519"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft 團隊中的保留原則

團隊交談預設為持續性，且預設為永久保留。 隨著保留原則的推出，系統管理員可以在 [安全性 & 合規性中心中設定保留原則（保留與刪除），以供小組聊天和頻道訊息使用。 此功能可協助組織針對特定期間保留資料，以進行合規性（亦即保留原則），或去除資料（亦即刪除原則）（如果在特定期間內被視為負債）。 團隊保留原則可確保在您刪除資料時，會從團隊服務上的所有永久資料儲存位置中移除資料。

> [!NOTE]
> 我們還不支援保留私人通道訊息的設定。 支援在私人通道中共用的檔案保留。

若要管理團隊保留原則，請在 [**資訊管理** > **保留**] 底下的 [Office 365 安全性 & 規範中心中使用設定和 Cmdlet。

團隊保留原則支援： 
    
- [保留]：將團隊資料保持在指定的持續時間內，然後執行任何動作
- 保留並刪除：將團隊資料保留指定工期，然後刪除
- 刪除：在指定的時間之後刪除團隊資料

團隊保留原則尚不支援：

- [高級保留原則] 不適用於小組聊天與團隊頻道訊息位置
- 持續天數少於30天

系統管理員可以為小組私人聊天設定個別保留原則（1:1 或1：許多聊天）與團隊頻道訊息。 在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。 在安全性 & 合規性中心（**資訊管理** > **保留**）中設定這些原則。 開啟**團隊頻道訊息**與**團隊聊天**，然後定義這些位置的保留原則（也會顯示在下圖中）。 

當您開啟 [**小組頻道] 訊息**時，您可以指定此原則適用的小組。 例如，對於團隊 X、Y 和 Z，系統管理員可以將刪除原則設定為1年（透過個別選取這些團隊），然後將3年刪除原則套用到其餘的團隊。 

您可以選取特定使用者並套用唯一的保留原則，為**小組聊天**進行相同的工作。 

![[小組] 資料至 [Exchange] 和 [SharePoint] 的工作流程圖表。](media/Retention-Policies.png)


> [!IMPORTANT]
> 團隊頻道訊息位置和小組聊天位置只會解決儲存在 Exchange Online 信箱（使用者和群組信箱）中的小組交談。 郵件會從所有相關的儲存位置（亦即信箱、基底及聊天服務）中刪除。 
> 
> 若要管理小組檔案的保留原則，這些檔案儲存在商務用 OneDrive 和 SharePoint 中，請使用其保留原則。

根據設計，小組檔案的刪除原則是透過 SharePoint Online 和商務用 OneDrive 位置進行設定。 因此，原則可能會刪除小組聊天或頻道訊息中參照的檔案，然後再刪除這些郵件。 在此情況下，檔案仍會顯示在小組訊息中，但如果您按一下檔案，您會收到「找不到檔案」錯誤（如果有人從 SharePoint Online 或商務用 OneDrive 手動刪除檔案，也可能會發生這種情況。

如需設定 Office 365 保留原則的詳細資訊，請閱讀[保留原則的概覽](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。
 
