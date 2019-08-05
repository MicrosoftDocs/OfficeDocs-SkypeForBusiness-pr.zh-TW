---
title: 執行報表以顯示使用中的 StaffHub 使用量
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 瞭解如何執行報表以取得貴組織中作用中 StaffHub 使用者的清單。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d13052751a43f3dba3e17c12d8e66d9afaf9dd
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2019
ms.locfileid: "36184044"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="13939-103">執行報表以顯示使用中的 StaffHub 使用量</span><span class="sxs-lookup"><span data-stu-id="13939-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13939-104">2019年10月1日生效, Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="13939-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="13939-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="13939-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="13939-106">今天, 小組包含針對排程管理的倒班應用程式, 而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="13939-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="13939-107">StaffHub 將會停止針對2019年10月1日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="13939-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="13939-108">任何試圖開啟 StaffHub 的人, 都會顯示一則訊息, 讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="13939-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="13939-109">若要深入瞭解, 請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="13939-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="13939-110">請使用本文中的步驟執行報表, 以取得貴組織中作用中 StaffHub 使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="13939-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="13939-111">當您準備好要[將 StaffHub 團隊移至 Microsoft 團隊](move-staffhub-teams-to-shifts-in-teams.md)時, 這項資訊可能會很方便。</span><span class="sxs-lookup"><span data-stu-id="13939-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="13939-112">在報告中, 當您從 StaffHub 切換至小組時, 您就會知道您需要包含在通訊中的人員。</span><span class="sxs-lookup"><span data-stu-id="13939-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="13939-113">您必須具備 Azure AD Premium, 才能執行本文中的步驟。</span><span class="sxs-lookup"><span data-stu-id="13939-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="13939-114">登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="13939-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="13939-115">在左窗格中, 按一下 [ **Azure Active Directory**資源]。</span><span class="sxs-lookup"><span data-stu-id="13939-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="13939-116">按一下 [**監視**] 底下的 [登**入**]。</span><span class="sxs-lookup"><span data-stu-id="13939-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="13939-117">在 [**應用程式**] 底下, 輸入 [ **Microsoft StaffHub**]。</span><span class="sxs-lookup"><span data-stu-id="13939-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="13939-118">為報表設定您想要的日期範圍, 然後按一下 [套用\*\*\*\*]。</span><span class="sxs-lookup"><span data-stu-id="13939-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![螢幕擷取畫面顯示如何顯示作用中 StaffHub 使用方式的相關步驟](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="13939-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="13939-120">Related topics</span></span>

- [<span data-ttu-id="13939-121">將 Microsoft StaffHub 小組移至 Microsoft 團隊中的倒班</span><span class="sxs-lookup"><span data-stu-id="13939-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
