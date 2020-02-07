---
title: 設定Skype 會議應用程式以搭配使用 Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 系統管理員可以使用 Microsoft 團隊系統管理中心來設定 Skype 會議應用程式與團隊搭配運作
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6d2725b3419283d5588882356c7334bb3d33405
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825521"
---
<a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="d635d-103">設定Skype 會議應用程式以搭配使用 Teams</span><span class="sxs-lookup"><span data-stu-id="d635d-103">Configure the Skype Meetings App to work with Teams</span></span>
===================================================

<span data-ttu-id="d635d-104">在使用者升級至 Microsoft 團隊之後，系統管理員可以使用 Microsoft 團隊系統管理中心來指定使用者將用來加入商務用 Skype 會議的喜好 app。</span><span class="sxs-lookup"><span data-stu-id="d635d-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="d635d-105">若要指定會議 Skype App 做為慣用的 app：</span><span class="sxs-lookup"><span data-stu-id="d635d-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="d635d-106">登入 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="d635d-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="d635d-107">在左窗格中的 [**整個組織的設定**] 底下，選取 [**團隊升級**]。</span><span class="sxs-lookup"><span data-stu-id="d635d-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="d635d-108">在 [團隊升級] 頁面上的 [**應用程式喜好**設定] 底下，從 [**供使用者加入商務用 Skype 會議**] 下拉式清單中，選取 [ **skype 會議] app** 。</span><span class="sxs-lookup"><span data-stu-id="d635d-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![為使用者選擇要加入商務用 Skype 會議的 [喜好 app]](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="d635d-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="d635d-110">Known limitations</span></span>

<span data-ttu-id="d635d-111">在團隊中使用 Skype 會議應用程式的使用者受到下列限制：</span><span class="sxs-lookup"><span data-stu-id="d635d-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="d635d-112">使用者沒有變更其影片裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="d635d-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="d635d-113">在使用者升級至團隊之後，如果使用者是在會議中使用 Skype 會議應用程式，然後接聽團隊通話，Skype 會議應用程式中的會議就不會置於保留狀態。</span><span class="sxs-lookup"><span data-stu-id="d635d-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="d635d-114">相反地，使用者會連接兩個通話。</span><span class="sxs-lookup"><span data-stu-id="d635d-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="d635d-115">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d635d-115">More information</span></span>

- [<span data-ttu-id="d635d-116">什麼是 Skype 會議應用程式（商務用 Skype Web App）</span><span class="sxs-lookup"><span data-stu-id="d635d-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- [<span data-ttu-id="d635d-117">Skype 會議 App 最低網路需求</span><span class="sxs-lookup"><span data-stu-id="d635d-117">Skype Meetings App minimum network requirements</span></span>](https://technet.microsoft.com/library/mt845808.aspx)
