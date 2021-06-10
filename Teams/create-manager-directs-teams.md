---
title: 在公司中建立Microsoft Teams
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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094409"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="017b5-103">在公司中建立Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="017b5-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="017b5-104">當您推出Microsoft Teams，而不是使用「空白 (無團隊或頻道) ，我們強烈建議您設定團隊和頻道的基本架構。</span><span class="sxs-lookup"><span data-stu-id="017b5-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="017b5-105">這有助於防止「團隊擴張」，讓使用者在應該要建立現有團隊的頻道時，建立許多團隊。</span><span class="sxs-lookup"><span data-stu-id="017b5-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="017b5-106">為了協助您開始使用設計良好的團隊和頻道結構，我們建立了 PowerShell 腳本，為每位第一線和第二線人員主管建立一個團隊，每位主管的直接主管都是小組成員。</span><span class="sxs-lookup"><span data-stu-id="017b5-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="017b5-107">這是「時間點」腳本 (不會在新增或移除組織成員時自動更新您的小組或) 。</span><span class="sxs-lookup"><span data-stu-id="017b5-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="017b5-108">但這是一個寶貴的工具，您可以從一開始在結構上Teams一些訂單。</span><span class="sxs-lookup"><span data-stu-id="017b5-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="017b5-109">此腳本會朗讀您的 Azure AD，並獲取管理員及其直接下屬的清單。</span><span class="sxs-lookup"><span data-stu-id="017b5-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="017b5-110">它會使用此清單來為每個人員管理員建立一個團隊。</span><span class="sxs-lookup"><span data-stu-id="017b5-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="017b5-111">如何使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="017b5-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="017b5-112">首先，請執行匯出管理員及其直接命令[腳本 (假設](scripts/powershell-script-create-teams-from-managers-export-managers.md)您已經執行[連線-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[連線-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模組) 。</span><span class="sxs-lookup"><span data-stu-id="017b5-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="017b5-113">匯出 *管理員及其直接命令* 腳本會建立定位字元分隔的檔案 (ExportedManagerDirects.txt) 列出所有主管及其直接下屬。</span><span class="sxs-lookup"><span data-stu-id="017b5-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="017b5-114">接著，執行 [建立新人員管理員團隊腳本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="017b5-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="017b5-115">此腳本會ExportedManagerDirects.txt檔案中，並為每個主管建立一個團隊，其中該主管的直接下屬是成員。</span><span class="sxs-lookup"><span data-stu-id="017b5-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="017b5-116">如果有任何主管或直接Teams，腳本會略過他們，不會建立團隊。</span><span class="sxs-lookup"><span data-stu-id="017b5-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="017b5-117"> (檢查報表，然後在開啟腳本後重新執行腳本Teams任何需要它的人。</span><span class="sxs-lookup"><span data-stu-id="017b5-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="017b5-118">腳本不會為已經建立團隊的任何主管建立第二個) </span><span class="sxs-lookup"><span data-stu-id="017b5-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="017b5-119">針對每個團隊，腳本會建立一個 「一般」和「只是為了好玩」頻道。</span><span class="sxs-lookup"><span data-stu-id="017b5-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="017b5-120">最佳做法</span><span class="sxs-lookup"><span data-stu-id="017b5-120">Best practices</span></span>

- <span data-ttu-id="017b5-121">要求每位人員管理員將貴組織的危機通訊網站新增為每個小組的一般頻道的一個定位停駐點。</span><span class="sxs-lookup"><span data-stu-id="017b5-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="017b5-122">閱讀此 2020 年 3 月 8 日部落格文章：使用 Microsoft Teams [+ Power Platform 協調Microsoft Teams通訊，以查看新的危機通訊應用程式](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。</span><span class="sxs-lookup"><span data-stu-id="017b5-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="017b5-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="017b5-123">Related topics</span></span>

[<span data-ttu-id="017b5-124">組織團隊的最佳作法</span><span class="sxs-lookup"><span data-stu-id="017b5-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="017b5-125">在 Teams 中建立全組織小組</span><span class="sxs-lookup"><span data-stu-id="017b5-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)