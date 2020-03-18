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
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="972f5-103">在 Microsoft 團隊中建立人員管理員小組</span><span class="sxs-lookup"><span data-stu-id="972f5-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="972f5-104">當您推出 Microsoft 團隊，而不是使用「空白平板」（無團隊或頻道）啟動時，強烈建議您設定團隊和頻道的基本架構。</span><span class="sxs-lookup"><span data-stu-id="972f5-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="972f5-105">這有助於防止「團隊大量增加」，使用者在應在現有團隊中建立頻道時，就會建立大量的團隊。</span><span class="sxs-lookup"><span data-stu-id="972f5-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="972f5-106">為了協助您開始使用精心設計的團隊和頻道結構，我們已建立 PowerShell 腳本，為第一和第二行人員管理員建立小組，並將每位經理的直接下屬做為小組成員。</span><span class="sxs-lookup"><span data-stu-id="972f5-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="972f5-107">這是「時間點」腳本（在組織中新增或移除人員時，不會自動更新您的團隊或頻道）。</span><span class="sxs-lookup"><span data-stu-id="972f5-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="972f5-108">但這是一個非常實用的工具，可讓您從開始就將某些訂單強加給您的小組結構。</span><span class="sxs-lookup"><span data-stu-id="972f5-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="972f5-109">此腳本會讀取您的 Azure AD，取得管理員及其直接下屬的清單。</span><span class="sxs-lookup"><span data-stu-id="972f5-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="972f5-110">它會使用此清單來針對每位人員管理員建立一個團隊。</span><span class="sxs-lookup"><span data-stu-id="972f5-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="972f5-111">如何使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="972f5-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="972f5-112">首先，執行[匯出管理員及其指引腳本](scripts/powershell-script-create-teams-from-managers-export-managers.md)（假設您已執行[連接 AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)和[MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 模組）。</span><span class="sxs-lookup"><span data-stu-id="972f5-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="972f5-113">*匯出管理員及其指導*式腳本會建立一個以 tab 分隔的檔案（ExportedManagerDirects），並以其直接下屬的方式列出所有管理員。</span><span class="sxs-lookup"><span data-stu-id="972f5-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="972f5-114">然後，執行 [[建立新的人員管理員小組] 腳本](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="972f5-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="972f5-115">此腳本會讀取 ExportedManagerDirects 檔案，並為每個管理員建立小組，並讓該主管的直接下屬成為成員。</span><span class="sxs-lookup"><span data-stu-id="972f5-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="972f5-116">如果有任何主管或 direct 沒有為團隊啟用任何管理員，則腳本會跳過它們，而且不會建立小組。</span><span class="sxs-lookup"><span data-stu-id="972f5-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="972f5-117">（請查看報表，然後在您開啟團隊以供需要的人員之後，再重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="972f5-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="972f5-118">此腳本將無法為已建立小組的任何主管建立第二個小組。</span><span class="sxs-lookup"><span data-stu-id="972f5-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="972f5-119">針對每個小組，此腳本會建立一般的「只是為了趣味」頻道。</span><span class="sxs-lookup"><span data-stu-id="972f5-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="972f5-120">最佳作法</span><span class="sxs-lookup"><span data-stu-id="972f5-120">Best practices</span></span>

- <span data-ttu-id="972f5-121">要求每位人員管理員將貴組織的危機通訊網站新增為每個小組之 [一般] 頻道的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="972f5-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="972f5-122">請閱讀2020年3月8日的博客文章：[使用 Microsoft 團隊 + Power Platform 進行危機通訊](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)，以查看新的危機通訊 app。</span><span class="sxs-lookup"><span data-stu-id="972f5-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="972f5-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="972f5-123">Related topics</span></span>

[<span data-ttu-id="972f5-124">組織團隊的最佳做法</span><span class="sxs-lookup"><span data-stu-id="972f5-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="972f5-125">在 Teams 中建立全組織小組</span><span class="sxs-lookup"><span data-stu-id="972f5-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
