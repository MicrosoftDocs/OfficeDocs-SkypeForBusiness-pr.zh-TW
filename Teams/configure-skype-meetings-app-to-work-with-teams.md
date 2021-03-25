---
title: 設定Skype 會議應用程式以搭配使用 Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 系統管理員可以使用 Microsoft Teams 系統管理中心來設定 Skype 會議應用程式以使用 Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40b1e0b95eeac06a0a92264305e0bf20e222d72e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122317"
---
<a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="b013f-103">設定Skype 會議應用程式以搭配使用 Teams</span><span class="sxs-lookup"><span data-stu-id="b013f-103">Configure the Skype Meetings App to work with Teams</span></span>
===================================================

<span data-ttu-id="b013f-104">將使用者升級至 Microsoft Teams 之後，系統管理員可以使用 Microsoft Teams 系統管理中心來指定使用者將用於加入商務用 Skype 會議的首選應用程式。</span><span class="sxs-lookup"><span data-stu-id="b013f-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="b013f-105">若要將 Skype 會議應用程式指定為偏好的應用程式：</span><span class="sxs-lookup"><span data-stu-id="b013f-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="b013f-106">登入 Microsoft Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="b013f-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="b013f-107">在左窗格中的 **全組織設定下**，選取 **Teams 升級**。</span><span class="sxs-lookup"><span data-stu-id="b013f-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="b013f-108">在 Teams 升級頁面上的 **App 喜好** 設定下，從使用者加入 **商務** 用 **Skype** 會議下拉式清單的偏好應用程式選取 Skype 會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="b013f-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![選擇使用者加入商務用 Skype 會議的首選應用程式](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="b013f-110">已知限制</span><span class="sxs-lookup"><span data-stu-id="b013f-110">Known limitations</span></span>

<span data-ttu-id="b013f-111">在 Teams 中使用 Skype 會議應用程式的使用者受下列限制：</span><span class="sxs-lookup"><span data-stu-id="b013f-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="b013f-112">使用者沒有變更其視像裝置的選項。</span><span class="sxs-lookup"><span data-stu-id="b013f-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="b013f-113">將使用者升級至 Teams 之後，如果使用者使用 Skype 會議應用程式參加會議，然後收到 Teams 上的通話，Skype 會議 App 中的會議不會保留。</span><span class="sxs-lookup"><span data-stu-id="b013f-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="b013f-114">而是將使用者連接到這兩個通話。</span><span class="sxs-lookup"><span data-stu-id="b013f-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="b013f-115">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b013f-115">More information</span></span>

- [<span data-ttu-id="b013f-116">什麼是 Skype 會議應用程式 (商務用 Skype Web App) </span><span class="sxs-lookup"><span data-stu-id="b013f-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- <span data-ttu-id="b013f-117">[Skype 會議 App 最低網路需求](/previous-versions/office/communications/mt845808(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="b013f-117">[Skype Meetings App minimum network requirements](/previous-versions/office/communications/mt845808(v=ocs.16))</span></span>