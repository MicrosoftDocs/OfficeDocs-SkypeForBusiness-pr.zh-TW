---
title: 管理 Education Insights 的使用者存取權
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 管理 Microsoft Teams 中 Education Insights 的使用者存取權。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145931"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="0d07c-103">管理 Education Insights 的使用者存取權</span><span class="sxs-lookup"><span data-stu-id="0d07c-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="0d07c-104">本文件提供管理[Microsoft Teams 中的 Education Insights](class-insights.md) 使用者存取權的必要步驟。</span><span class="sxs-lookup"><span data-stu-id="0d07c-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="0d07c-105">您必須為教育領導者、校區領導者、學校校長、首席教師、顧問、學習領域主任、計畫主任、社交工作者和心理學家提供權限。</span><span class="sxs-lookup"><span data-stu-id="0d07c-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="0d07c-106">當授課者擁有班級團隊時，系統就會 *自動* 提供其權限。</span><span class="sxs-lookup"><span data-stu-id="0d07c-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="0d07c-107">若要提供組織層級 Insights，您必須[從學生資訊系統 (SIS) 匯入資訊](education-insights-sis-data-sync.md)，讓 Insights 會有正確對應的教育系統階層結構。</span><span class="sxs-lookup"><span data-stu-id="0d07c-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="0d07c-108">只有全域系統管理員才能管理 Insights 的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="0d07c-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="0d07c-109">我們建議您為您的所有教育領導者啟用 Insights，讓他們有資料可以了解每所學校，並且可以快速識別問題並且為教育人員提供支援。</span><span class="sxs-lookup"><span data-stu-id="0d07c-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="0d07c-110">即使您正在執行試驗，為所有教育領導者保持 Insights 啟用仍然有幫助，但是僅將通訊目標限定為試驗使用者群組。</span><span class="sxs-lookup"><span data-stu-id="0d07c-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="0d07c-111">授與權限</span><span class="sxs-lookup"><span data-stu-id="0d07c-111">Grant permissions</span></span>

* <span data-ttu-id="0d07c-112">開啟 Insights 應用程式，按一下 **[設定]**，然後選取 **[使用者權限]**</span><span class="sxs-lookup"><span data-stu-id="0d07c-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定":::

* <span data-ttu-id="0d07c-114">選取 **[新增使用者]**。</span><span class="sxs-lookup"><span data-stu-id="0d07c-114">Select **Add users**.</span></span>
* <span data-ttu-id="0d07c-115">輸入每個使用者的使用者名稱或電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0d07c-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="0d07c-116">選取權限等級：</span><span class="sxs-lookup"><span data-stu-id="0d07c-116">Select the permission level:</span></span>
  * <span data-ttu-id="0d07c-117">**所有組織的存取權** 表示使用者會看到所有層級的所有組織單位。</span><span class="sxs-lookup"><span data-stu-id="0d07c-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="0d07c-118">**特定學校的存取權** 表示使用者會看到選取的學校。</span><span class="sxs-lookup"><span data-stu-id="0d07c-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="0d07c-119">開始輸入，然後從清單中選取學校。</span><span class="sxs-lookup"><span data-stu-id="0d07c-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="0d07c-120">您可以一併新增多所學校。</span><span class="sxs-lookup"><span data-stu-id="0d07c-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="0d07c-121">按一下 **[新增使用者]**。</span><span class="sxs-lookup"><span data-stu-id="0d07c-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="授與權限":::

> [!NOTE]
> <span data-ttu-id="0d07c-123">僅將權限提供給需要的教育領導者，並僅限他們負責的組織單位。</span><span class="sxs-lookup"><span data-stu-id="0d07c-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="0d07c-124">如果您不確定是否需要特定組織的使用者權限，請洽詢您機構的隱私權主題專家，例如法務或人力資源人員。</span><span class="sxs-lookup"><span data-stu-id="0d07c-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="0d07c-125">編輯權限</span><span class="sxs-lookup"><span data-stu-id="0d07c-125">Edit permissions</span></span>
* <span data-ttu-id="0d07c-126">選取特定使用者，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0d07c-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="0d07c-127">更新權限等級或學校清單，然後按一下 **[更新權限]**。</span><span class="sxs-lookup"><span data-stu-id="0d07c-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="編輯權限":::

## <a name="remove-permissions"></a><span data-ttu-id="0d07c-129">移除權限</span><span class="sxs-lookup"><span data-stu-id="0d07c-129">Remove permissions</span></span>
* <span data-ttu-id="0d07c-130">選取您要移除的使用者，然後選取 **[移除使用者]**。</span><span class="sxs-lookup"><span data-stu-id="0d07c-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="0d07c-131">這些使用者無法再存取組織層級 Insights，但是如果他們擁有課程小組，仍然可以存取課程層級 Insights。</span><span class="sxs-lookup"><span data-stu-id="0d07c-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="移除權限":::
