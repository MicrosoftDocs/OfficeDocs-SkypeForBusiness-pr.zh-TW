---
title: 在 Teams 中建立人員管理團隊Microsoft
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 瞭解如何使用 PowerShell 腳本為每個主管建立團隊，並以其直接的團隊成員身分建立團隊。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198925"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Teams 中建立人員管理團隊Microsoft


當您推出 teams Microsoft，而不是以「空白白板」啟動， (沒有團隊或頻道) ，我們強烈建議您設定團隊和頻道的基礎架構。 這有助於防止使用者在現有團隊中建立頻道時，在其中建立多個團隊。 為了協助您開始使用設計完善的團隊和頻道結構，我們建立了 PowerShell 腳本，為每個第一行和第二線人員經理建立一個團隊，每個主管的直接報告都是團隊成員。 這是「時間點」腳本， (不會在使用者從組織) 新增或移除人員時自動更新您的團隊或頻道。 但這是一項寶貴的工具，可讓您從一開始就對 Teams 結構施加一些順序。 此腳本會朗讀您的 Azure AD、取得經理清單及其直接報告。 它會使用這份清單來為每位人員經理建立一個團隊。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 腳本 

首先，執行 [匯出管理員及其直接專案腳本](scripts/powershell-script-create-teams-from-managers-export-managers.md) (，假設您已經執行 [Connect-AzureAd](/powershell/module/azuread/connect-azuread) 和 [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell 模組) 。 *匯出管理員及其直接* 指令腳本會建立定位字元分隔檔案 (ExportedManagerDirects.txt) ，其中會列出所有管理員的直接報表。 

然後，執行 [[建立新的人員管理團隊] 腳本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此腳本會讀取ExportedManagerDirects.txt檔案，並為每個主管建立一個團隊，並將該主管的直接報告作為成員。 如果 Teams 未啟用任何經理或直接主管，腳本會跳過這些專案，而不會建立團隊。  (檢閱報告，然後在您為任何需要的人員開啟 Teams 之後重新執行腳本。 腳本不會為已經建立團隊的任何經理建立第二個團隊。

腳本會為每個團隊建立 [一般] 和 [只是為了好玩] 頻道。 

## <a name="best-practices"></a>最佳做法

- 要求每位人員管理員將貴組織的當機通訊網站新增為每個小組的 [一般] 頻道索引標籤。 

- 請閱讀這篇 2020 年 3 月 8 日的部落格文章來查看新的「問題溝通」應用程式：[使用 Microsoft Teams + Power Platform 協調問題溝通](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。

## <a name="related-topics"></a>相關主題

[組織團隊的最佳做法](best-practices-organizing.md)

[在 Teams 中建立全組織小組](create-an-org-wide-team.md)