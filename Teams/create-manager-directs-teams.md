---
title: 在 Microsoft 團隊中建立人員管理員小組
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 瞭解如何使用 PowerShell 腳本，為每個主管建立小組，並將其指引做為小組成員。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796199"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft 團隊中建立人員管理員小組


當您推出 Microsoft 團隊，而不是使用「空白平板」（無團隊或頻道）啟動時，強烈建議您設定團隊和頻道的基本架構。 這有助於防止「團隊大量增加」，使用者在應在現有團隊中建立頻道時，就會建立大量的團隊。 為了協助您開始使用精心設計的團隊和頻道結構，我們已建立 PowerShell 腳本，為第一和第二行人員管理員建立小組，並將每位經理的直接下屬做為小組成員。 這是「時間點」腳本（在組織中新增或移除人員時，不會自動更新您的團隊或頻道）。 但這是一個非常實用的工具，可讓您從開始就將某些訂單強加給您的小組結構。 此腳本會讀取您的 Azure AD，取得管理員及其直接下屬的清單。 它會使用此清單來針對每位人員管理員建立一個團隊。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 腳本 

首先，執行[匯出管理員及其指引腳本](scripts/powershell-script-create-teams-from-managers-export-managers.md)（假設您已執行[連接 AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模組）。 *匯出管理員及其指導*式腳本會建立一個以 tab 分隔的檔案（ExportedManagerDirects），並以其直接下屬的方式列出所有管理員。 

然後，執行 [[建立新的人員管理員小組] 腳本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此腳本會讀取 ExportedManagerDirects 檔案，並為每個管理員建立小組，並讓該主管的直接下屬成為成員。 如果有任何主管或 direct 沒有為團隊啟用任何管理員，則腳本會跳過它們，而且不會建立小組。 （請查看報表，然後在您開啟團隊以供需要的人員之後，再重新執行腳本。 此腳本將無法為已建立小組的任何主管建立第二個小組。

針對每個小組，此腳本會建立一般的「只是為了趣味」頻道。 

## <a name="best-practices"></a>最佳作法

- 要求每位人員管理員將貴組織的危機通訊網站新增為每個小組之 [一般] 頻道的索引標籤。 

- 請閱讀2020年3月8日的博客文章：[使用 Microsoft 團隊 + Power Platform 進行危機通訊](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)，以查看新的危機通訊 app。

## <a name="related-topics"></a>相關主題

[組織團隊的最佳做法](best-practices-organizing.md)

[在 Teams 中建立全組織小組](create-an-org-wide-team.md)
