---
title: 使用會議室服務Microsoft Teams角色進階版存取控制
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解使用受管理服務Microsoft Teams 會議室存取控制。
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662598"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a><span data-ttu-id="f6461-103">使用受管理服務的角色Microsoft Teams 會議室存取控制</span><span class="sxs-lookup"><span data-stu-id="f6461-103">Role-based access control with the Microsoft Teams Rooms managed service</span></span>

<span data-ttu-id="f6461-104">在受管理的服務 (RBAC) 中Microsoft Teams 會議室角色式存取控制，可協助管理使用者對貴組織中會議室資源資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="f6461-104">Role-based access control (RBAC) in the Microsoft Teams Rooms managed service helps you manage user access to room resource data in your organization.</span></span> <span data-ttu-id="f6461-105">將角色指派給服務入口網站使用者，您可以限制他們可以看到和變更的內容。</span><span class="sxs-lookup"><span data-stu-id="f6461-105">By assigning roles to your service portal users, you can limit what they can see and change.</span></span> <span data-ttu-id="f6461-106">每個角色都有一組許可權，可決定哪些具有該角色的使用者可以在貴組織中存取及變更。</span><span class="sxs-lookup"><span data-stu-id="f6461-106">Each role has a set of permissions that determine what users with that role can access and change within your organization.</span></span>

<span data-ttu-id="f6461-107">若要建立、編輯或指派角色，您的帳戶必須具有下列其中一項許可權：</span><span class="sxs-lookup"><span data-stu-id="f6461-107">To create, edit, or assign roles, your account must have one of the following permissions:</span></span>

- <span data-ttu-id="f6461-108">透過 Azure AD Azure Active Directory (全域系統管理員) </span><span class="sxs-lookup"><span data-stu-id="f6461-108">Global Administrator through Azure Active Directory (Azure AD)</span></span>
- <span data-ttu-id="f6461-109">透過受管理的服務入口網站Microsoft Teams 會議室服務管理員</span><span class="sxs-lookup"><span data-stu-id="f6461-109">Managed Service Administrator through the Microsoft Teams Rooms managed service portal</span></span>

## <a name="what-is-a-role"></a><span data-ttu-id="f6461-110">什麼是角色？</span><span class="sxs-lookup"><span data-stu-id="f6461-110">What is a role?</span></span>

<span data-ttu-id="f6461-111">角色會定義指派給該角色的使用者所授予的許可權集。</span><span class="sxs-lookup"><span data-stu-id="f6461-111">A role defines the set of permissions granted to users assigned to that role.</span></span> <span data-ttu-id="f6461-112">目前，受Microsoft Teams 會議室服務有三個內建角色：Managed **Service 系統管理員**、**網站潛在客戶** 和 **網站技術**。</span><span class="sxs-lookup"><span data-stu-id="f6461-112">For now, the Microsoft Teams Rooms managed service has three built-in roles: **Managed Service Administrator**, **Site Lead**, and **Site Tech**.</span></span> <span data-ttu-id="f6461-113">它們涵蓋組織中可能參與管理您會議室的一些常見案例。</span><span class="sxs-lookup"><span data-stu-id="f6461-113">They cover some common scenarios for users in your organization that may be involved in managing your rooms.</span></span>

<span data-ttu-id="f6461-114">若要查看角色，請在 Microsoft Teams 會議室 受管理服務入口網站左側流覽中，前往角色，然後選取任何角色以查看角色的屬性、許可權和指派。</span><span class="sxs-lookup"><span data-stu-id="f6461-114">To see roles, in the left navigation of the Microsoft Teams Rooms managed service portal, go to **Roles**, and then select any of the roles to see the role’s properties, permissions, and assignments.</span></span>  

- <span data-ttu-id="f6461-115">**屬性**：名稱、角色類型和描述</span><span class="sxs-lookup"><span data-stu-id="f6461-115">**Properties**: The name, role type, and description</span></span>
- <span data-ttu-id="f6461-116">**許可權**：列出角色有權存取的功能和許可權等級。</span><span class="sxs-lookup"><span data-stu-id="f6461-116">**Permissions**: Lists features and level of permissions to which the role has access.</span></span>
- <span data-ttu-id="f6461-117">**指派**：角色指派清單，定義哪些使用者擁有會議室資源帳戶範圍的許可權。</span><span class="sxs-lookup"><span data-stu-id="f6461-117">**Assignments**: A list of role assignments defining which users have the configured permissions over the scope of room resource accounts.</span></span> <span data-ttu-id="f6461-118">角色可以有多個工作分派，而使用者可以有多個工作分派。</span><span class="sxs-lookup"><span data-stu-id="f6461-118">A role can have multiple assignments, and a user can be in multiple assignments.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="f6461-119">內建角色</span><span class="sxs-lookup"><span data-stu-id="f6461-119">Built-in roles</span></span>

<span data-ttu-id="f6461-120">您可以指派內建角色給群組或使用者，而不進行進一步配置。</span><span class="sxs-lookup"><span data-stu-id="f6461-120">You can assign built-in roles to groups or users without further configuration.</span></span> <span data-ttu-id="f6461-121">請記住，您無法刪除或編輯內建角色的名稱、描述、類型或許可權。</span><span class="sxs-lookup"><span data-stu-id="f6461-121">Keep in mind that you can't delete or edit the name, description, type, or permissions of a built-in role.</span></span>

- <span data-ttu-id="f6461-122">**Managed Service 系統管理員**：擁有會議室Microsoft Teams服務進階版的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="f6461-122">**Managed Service Administrator**: Has full access to the Microsoft Teams Room Premium service portal.</span></span>
- <span data-ttu-id="f6461-123">**網站潛在客戶**：整理會議室、存取報表，以及管理票證。</span><span class="sxs-lookup"><span data-stu-id="f6461-123">**Site Lead**: Organizes rooms, has access to reports and can manage tickets.</span></span> <span data-ttu-id="f6461-124">無法重設註冊金鑰，或變更服務的設定。</span><span class="sxs-lookup"><span data-stu-id="f6461-124">Can't reset enrollment key or make changes to the configuration of the service.</span></span>  
- <span data-ttu-id="f6461-125">**網站技術**：管理特定會議室的票證。</span><span class="sxs-lookup"><span data-stu-id="f6461-125">**Site Tech**: Manages tickets for specific rooms.</span></span> <span data-ttu-id="f6461-126">沒有修改服務或組織服務中聊天室的許可權。</span><span class="sxs-lookup"><span data-stu-id="f6461-126">Doesn't have permissions to modify the service or organize rooms in the service.</span></span>

<span data-ttu-id="f6461-127">下表摘要列出每個角色可以執行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="f6461-127">The following table summarizes what each role can do.</span></span>

|<span data-ttu-id="f6461-128">功能</span><span class="sxs-lookup"><span data-stu-id="f6461-128">Features</span></span> |<span data-ttu-id="f6461-129">許可</span><span class="sxs-lookup"><span data-stu-id="f6461-129">Permission</span></span> |<span data-ttu-id="f6461-130">Managed Service 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f6461-130">Managed Service Administrator</span></span>  |<span data-ttu-id="f6461-131">網站潛在客戶</span><span class="sxs-lookup"><span data-stu-id="f6461-131">Site Lead</span></span>  |<span data-ttu-id="f6461-132">網站技術</span><span class="sxs-lookup"><span data-stu-id="f6461-132">Site Tech</span></span>  |
|---------|---------|---------|---------|---------|
|<span data-ttu-id="f6461-133">房間</span><span class="sxs-lookup"><span data-stu-id="f6461-133">Rooms</span></span>     |<span data-ttu-id="f6461-134">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-134">View</span></span>        |<span data-ttu-id="f6461-135">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-135">&#10004;</span></span>           |<span data-ttu-id="f6461-136">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-136">&#10004;</span></span>           |<span data-ttu-id="f6461-137">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-137">&#10004;</span></span>  |
|    |<span data-ttu-id="f6461-138">修改</span><span class="sxs-lookup"><span data-stu-id="f6461-138">Modify</span></span>         |<span data-ttu-id="f6461-139">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-139">&#10004;</span></span>           |<span data-ttu-id="f6461-140">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-140">&#10004;</span></span>           |<span data-ttu-id="f6461-141">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-141">&#10004;</span></span> |
|    |<span data-ttu-id="f6461-142">重設按鍵</span><span class="sxs-lookup"><span data-stu-id="f6461-142">Reset key</span></span>         |<span data-ttu-id="f6461-143">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-143">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="f6461-144">下載金鑰</span><span class="sxs-lookup"><span data-stu-id="f6461-144">Download key</span></span>         |<span data-ttu-id="f6461-145">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-145">&#10004;</span></span>           |<span data-ttu-id="f6461-146">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-146">&#10004;</span></span>          |<span data-ttu-id="f6461-147">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-147">&#10004;</span></span> |
|    |<span data-ttu-id="f6461-148">取消註冊</span><span class="sxs-lookup"><span data-stu-id="f6461-148">Unenroll</span></span>         |<span data-ttu-id="f6461-149">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-149">&#10004;</span></span>           |<span data-ttu-id="f6461-150">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-150">&#10004;</span></span>           |<span data-ttu-id="f6461-151">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-151">&#10004;</span></span> |
|<span data-ttu-id="f6461-152">群組管理</span><span class="sxs-lookup"><span data-stu-id="f6461-152">Group management</span></span>   |<span data-ttu-id="f6461-153">創建</span><span class="sxs-lookup"><span data-stu-id="f6461-153">Create</span></span>         |<span data-ttu-id="f6461-154">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-154">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="f6461-155">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-155">View</span></span>       |<span data-ttu-id="f6461-156">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-156">&#10004;</span></span>          |<span data-ttu-id="f6461-157">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-157">&#10004;</span></span>           ||
|    |<span data-ttu-id="f6461-158">修改</span><span class="sxs-lookup"><span data-stu-id="f6461-158">Modify</span></span>         |<span data-ttu-id="f6461-159">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-159">&#10004;</span></span>           |           ||
|<span data-ttu-id="f6461-160">更新響鈴管理</span><span class="sxs-lookup"><span data-stu-id="f6461-160">Update ring management</span></span>    |<span data-ttu-id="f6461-161">創建</span><span class="sxs-lookup"><span data-stu-id="f6461-161">Create</span></span>         |<span data-ttu-id="f6461-162">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-162">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="f6461-163">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-163">View</span></span>         |<span data-ttu-id="f6461-164">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-164">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="f6461-165">修改</span><span class="sxs-lookup"><span data-stu-id="f6461-165">Modify</span></span>         |<span data-ttu-id="f6461-166">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-166">&#10004;</span></span>           |           ||
|<span data-ttu-id="f6461-167">報告</span><span class="sxs-lookup"><span data-stu-id="f6461-167">Reports</span></span>   |<span data-ttu-id="f6461-168">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-168">View</span></span>        |<span data-ttu-id="f6461-169">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-169">&#10004;</span></span>           |<span data-ttu-id="f6461-170">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-170">&#10004;</span></span>           ||
|<span data-ttu-id="f6461-171">票證管理</span><span class="sxs-lookup"><span data-stu-id="f6461-171">Ticket management</span></span>   |<span data-ttu-id="f6461-172">建立客戶事件</span><span class="sxs-lookup"><span data-stu-id="f6461-172">Create customer incident</span></span>         |<span data-ttu-id="f6461-173">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-173">&#10004;</span></span>           |<span data-ttu-id="f6461-174">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-174">&#10004;</span></span>           |<span data-ttu-id="f6461-175">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-175">&#10004;</span></span>  |
|    |<span data-ttu-id="f6461-176">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-176">View</span></span>         |<span data-ttu-id="f6461-177">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-177">&#10004;</span></span>           |<span data-ttu-id="f6461-178">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-178">&#10004;</span></span>           |<span data-ttu-id="f6461-179">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-179">&#10004;</span></span>  |
|    |<span data-ttu-id="f6461-180">更新</span><span class="sxs-lookup"><span data-stu-id="f6461-180">Update</span></span>         |<span data-ttu-id="f6461-181">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-181">&#10004;</span></span>           |<span data-ttu-id="f6461-182">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-182">&#10004;</span></span>           |<span data-ttu-id="f6461-183">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-183">&#10004;</span></span>  |
|<span data-ttu-id="f6461-184">Microsoft Teams 會議室服務設定</span><span class="sxs-lookup"><span data-stu-id="f6461-184">Microsoft Teams Rooms managed service settings</span></span>    |<span data-ttu-id="f6461-185">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-185">View</span></span>         |<span data-ttu-id="f6461-186">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-186">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="f6461-187">修改</span><span class="sxs-lookup"><span data-stu-id="f6461-187">Modify</span></span>        |<span data-ttu-id="f6461-188">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-188">&#10004;</span></span>           |         ||
|<span data-ttu-id="f6461-189">角色管理</span><span class="sxs-lookup"><span data-stu-id="f6461-189">Role management</span></span>    |<span data-ttu-id="f6461-190">檢視</span><span class="sxs-lookup"><span data-stu-id="f6461-190">View</span></span>         |<span data-ttu-id="f6461-191">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-191">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="f6461-192">修改</span><span class="sxs-lookup"><span data-stu-id="f6461-192">Modify</span></span>         |<span data-ttu-id="f6461-193">&#10004;</span><span class="sxs-lookup"><span data-stu-id="f6461-193">&#10004;</span></span>           |         ||

## <a name="assign-a-role"></a><span data-ttu-id="f6461-194">指派角色</span><span class="sxs-lookup"><span data-stu-id="f6461-194">Assign a role</span></span>

<span data-ttu-id="f6461-195">若要指派角色，您必須是全域系統管理員或 Managed Service 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f6461-195">To assign roles, you must be a Global Administrator or Managed Service Administrator.</span></span>

1. <span data-ttu-id="f6461-196">在受管理服務入口網站左側Microsoft Teams 會議室，**請前往** 設定  >  **角色**。</span><span class="sxs-lookup"><span data-stu-id="f6461-196">In the left navigation of the Microsoft Teams Rooms managed service portal, go to **Settings** > **Roles**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="顯示角色的 Access 控制項頁面螢幕擷取畫面":::

2. <span data-ttu-id="f6461-198">選取您想要指派的角色。</span><span class="sxs-lookup"><span data-stu-id="f6461-198">Select the role you want to assign.</span></span>
3. <span data-ttu-id="f6461-199">在角色窗格中，選取指派  >  **新增**。</span><span class="sxs-lookup"><span data-stu-id="f6461-199">In the role pane, select **Assignments** > **Add**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="新增角色選項的螢幕擷取畫面。":::

4. <span data-ttu-id="f6461-201">在一 **般設定** 頁面的作業 **屬性** 下，輸入此作業的名稱。</span><span class="sxs-lookup"><span data-stu-id="f6461-201">On the **General settings** page, under **Assignment properties**, enter a name for this assignment.</span></span> <span data-ttu-id="f6461-202">描述為選擇性。</span><span class="sxs-lookup"><span data-stu-id="f6461-202">The description is optional.</span></span> <span data-ttu-id="f6461-203">選擇 **下一步。**</span><span class="sxs-lookup"><span data-stu-id="f6461-203">Choose **Next.**</span></span>
5. <span data-ttu-id="f6461-204">在成員 **頁面上** 的搜尋使用者或安全性群組方塊中，輸入您租使用者中要授予許可權的使用者或安全性群組名稱，然後完成選取專案。</span><span class="sxs-lookup"><span data-stu-id="f6461-204">On the **Members** page, in the **Search for user or security group** box, enter the name of a user or security group in your tenant to which you want to give permissions, and then complete the selection.</span></span> <span data-ttu-id="f6461-205">選擇下 **一個**。</span><span class="sxs-lookup"><span data-stu-id="f6461-205">Choose **Next**.</span></span> 
6. <span data-ttu-id="f6461-206">在範圍 **頁面上** 的搜尋會議室或會議室群組方塊中，輸入允許使用者管理的會議室或會議室群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f6461-206">On the **Scope** page, in the **Search for room or room group** box, type the name of either a room or room group that the user will be allowed to manage.</span></span> <span data-ttu-id="f6461-207">選擇下 **一個**。</span><span class="sxs-lookup"><span data-stu-id="f6461-207">Choose **Next**.</span></span>
7. <span data-ttu-id="f6461-208">在完成 **頁面上** ，查看作業詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f6461-208">On the **Finish** page, review the details of the assignment.</span></span> <span data-ttu-id="f6461-209">如果您對組組感到滿意，請選擇新增 **作業**。</span><span class="sxs-lookup"><span data-stu-id="f6461-209">If you're satisfied with the configuration, choose **Add assignment**.</span></span> <span data-ttu-id="f6461-210">如果您想要編輯節，請使用上一 **個按鈕，** 或選取左側導圖中的步驟。</span><span class="sxs-lookup"><span data-stu-id="f6461-210">If you want to edit a section, use the **Previous** button or select the step in the left navigation.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="f6461-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="f6461-211">Related topics</span></span>

- [<span data-ttu-id="f6461-212">Microsoft Teams 會議室管理服務</span><span class="sxs-lookup"><span data-stu-id="f6461-212">Microsoft Teams Rooms managed service</span></span>](microsoft-teams-rooms-premium.md)
