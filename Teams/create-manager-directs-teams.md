---
title: 在 Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 瞭解如何使用 PowerShell 腳本為每位主管建立團隊，並擔任團隊成員。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cad2ed4fdbcec7f13f5b2e932d34395fe4b4c339
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628355"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>在 Microsoft Teams


當您推出Microsoft Teams時，建議您設定團隊和頻道的基本架構，而不是使用「空白 (或頻道) 來啟動。 這有助於防止「團隊擴張」，讓使用者在應該要建立現有團隊的頻道時，建立許多團隊。 為了協助您開始使用設計良好的團隊和頻道結構，我們建立了 PowerShell 腳本，為每位第一線和第二線人員主管建立一個團隊，每位主管的直接主管都是小組成員。 這是「時間點」腳本 (不會在新增或移除組織成員時自動更新您的小組或頻道) 。 但這是一個寶貴的工具，您可以一開始在結構上Teams一些訂單。 此腳本會朗讀您的 Azure AD，並獲取管理員及其直接下屬的清單。 它會使用此清單來為每個人員管理員建立一個團隊。 

## <a name="how-to-use-the-powershell-script"></a>如何使用 PowerShell 腳本 

首先執行匯出管理員及其直接腳本[ (](scripts/powershell-script-create-teams-from-managers-export-managers.md)假設您已經執行[連線-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[連線-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模組) 。 匯出 *管理員及其直接命令* 腳本會建立一個定位字元分隔 (ExportedManagerDirects.txt) ，其中會列出所有主管及其直接下屬。 

然後，執行建立 [新人員管理員團隊腳本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。 此腳本會ExportedManagerDirects.txt檔案中，並為每個主管建立一個團隊，其中該主管的直接下屬是成員。 如果有任何主管或直接Teams，腳本會略過他們，不會建立團隊。  (檢查報表，然後在開啟腳本後重新執行Teams需要該腳本的人。 腳本不會為已經建立團隊的任何主管建立第二個) 

針對每個團隊，腳本會建立一個 「一般」和「只是為了好玩」頻道。 

## <a name="best-practices"></a>最佳做法

- 要求每位人員主管將貴組織的危機通訊網站新增為每個小組的一般頻道的一個定位停駐點。 

- 請閱讀 2020 年 3 月 8 日部落格文章：使用 Microsoft Teams + Power Platform 協調Microsoft Teams [App。](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>相關主題

[組織團隊的最佳作法](best-practices-organizing.md)

[在 Teams 中建立全組織小組](create-an-org-wide-team.md)