---
title: 使用 Microsoft 團隊聊天室 Premium 服務的角色式存取控制
author: lanachin
ms.author: v-lanac
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
description: 瞭解 Microsoft 團隊聊天室管理服務的角色式存取控制。
f1keywords: ''
ms.openlocfilehash: 2f3886d7f7f59521028b87f05ffedfaa1fae9ac2
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300287"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a><span data-ttu-id="ad3ae-103">使用 Microsoft 團隊聊天室管理服務的角色型存取控制</span><span class="sxs-lookup"><span data-stu-id="ad3ae-103">Role-based access control with the Microsoft Teams Rooms managed service</span></span>

<span data-ttu-id="ad3ae-104">在 Microsoft 團隊聊天室管理服務中 (RBAC) 的角色式存取控制可協助您管理使用者對組織中的聊天室資源資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-104">Role-based access control (RBAC) in the Microsoft Teams Rooms managed service helps you manage user access to room resource data in your organization.</span></span> <span data-ttu-id="ad3ae-105">透過指派角色給您的服務入口網站使用者，您可以限制他們可以查看和變更的專案。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-105">By assigning roles to your service portal users, you can limit what they can see and change.</span></span> <span data-ttu-id="ad3ae-106">每個角色都有一組許可權，決定擁有該角色的使用者可以在貴組織記憶體取及變更哪些使用者。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-106">Each role has a set of permissions that determine what users with that role can access and change within your organization.</span></span>

<span data-ttu-id="ad3ae-107">若要建立、編輯或指派角色，您的帳戶必須具備下列其中一項許可權：</span><span class="sxs-lookup"><span data-stu-id="ad3ae-107">To create, edit, or assign roles, your account must have one of the following permissions:</span></span>

- <span data-ttu-id="ad3ae-108">全域管理員（透過 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="ad3ae-108">Global Administrator through Azure Active Directory (Azure AD)</span></span>
- <span data-ttu-id="ad3ae-109">透過 Microsoft 團隊聊天室管理的服務入口網站管理的服務管理員</span><span class="sxs-lookup"><span data-stu-id="ad3ae-109">Managed Service Administrator through the Microsoft Teams Rooms managed service portal</span></span>

## <a name="what-is-a-role"></a><span data-ttu-id="ad3ae-110">何謂角色？</span><span class="sxs-lookup"><span data-stu-id="ad3ae-110">What is a role?</span></span>

<span data-ttu-id="ad3ae-111">角色定義授與指派給該角色之使用者的一組許可權。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-111">A role defines the set of permissions granted to users assigned to that role.</span></span> <span data-ttu-id="ad3ae-112">目前，Microsoft [小組聊天室] 管理服務有三個內建角色： **受管理的服務系統管理員**、 **網站主管**和 **網站技術**。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-112">For now, the Microsoft Teams Rooms managed service has three built-in roles: **Managed Service Administrator**, **Site Lead**, and **Site Tech**.</span></span> <span data-ttu-id="ad3ae-113">它們涵蓋貴組織中可能涉及管理您的聊天室的使用者的一些常見案例。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-113">They cover some common scenarios for users in your organization that may be involved in managing your rooms.</span></span>

<span data-ttu-id="ad3ae-114">若要查看角色，請在 Microsoft 團隊聊天室 managed 服務入口網站的左側導覽中，移至 [ **角色**]，然後選取任何角色，即可查看角色的屬性、許可權和作業。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-114">To see roles, in the left navigation of the Microsoft Teams Rooms managed service portal, go to **Roles**, and then select any of the roles to see the role’s properties, permissions, and assignments.</span></span>  

- <span data-ttu-id="ad3ae-115">[**屬性**]：名稱、角色類型及描述</span><span class="sxs-lookup"><span data-stu-id="ad3ae-115">**Properties**: The name, role type, and description</span></span>
- <span data-ttu-id="ad3ae-116">**許可權**：列出角色有權存取的功能和許可權等級。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-116">**Permissions**: Lists features and level of permissions to which the role has access.</span></span>
- <span data-ttu-id="ad3ae-117">**作業**：角色指派的清單，定義哪些使用者擁有房間資源帳戶範圍的設定許可權。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-117">**Assignments**: A list of role assignments defining which users have the configured permissions over the scope of room resource accounts.</span></span> <span data-ttu-id="ad3ae-118">角色可以有多個作業，而使用者可以有多個作業。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-118">A role can have multiple assignments, and a user can be in multiple assignments.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="ad3ae-119">內建角色</span><span class="sxs-lookup"><span data-stu-id="ad3ae-119">Built-in roles</span></span>

<span data-ttu-id="ad3ae-120">您可以將內建角色指派給群組或使用者，而無需進一步設定。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-120">You can assign built-in roles to groups or users without further configuration.</span></span> <span data-ttu-id="ad3ae-121">請記住，您無法刪除或編輯內建角色的名稱、描述、類型或許可權。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-121">Keep in mind that you can't delete or edit the name, description, type, or permissions of a built-in role.</span></span>

- <span data-ttu-id="ad3ae-122">**Managed Services 系統管理員**：擁有 Microsoft 團隊聊天室 Premium 服務入口網站的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-122">**Managed Service Administrator**: Has full access to the Microsoft Teams Room Premium service portal.</span></span>
- <span data-ttu-id="ad3ae-123">**網站領導**：組織工作室、存取報表並可管理票證。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-123">**Site Lead**: Organizes rooms, has access to reports and can manage tickets.</span></span> <span data-ttu-id="ad3ae-124">無法重設註冊金鑰或變更服務的設定。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-124">Can't reset enrollment key or make changes to the configuration of the service.</span></span>  
- <span data-ttu-id="ad3ae-125">**網站技術**：管理特定房間的票證。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-125">**Site Tech**: Manages tickets for specific rooms.</span></span> <span data-ttu-id="ad3ae-126">沒有許可權可以修改服務或管理服務中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-126">Doesn't have permissions to modify the service or organize rooms in the service.</span></span>

<span data-ttu-id="ad3ae-127">下表摘要列出每個角色所能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-127">The following table summarizes what each role can do.</span></span>

|<span data-ttu-id="ad3ae-128">功能</span><span class="sxs-lookup"><span data-stu-id="ad3ae-128">Features</span></span> |<span data-ttu-id="ad3ae-129">拒絕</span><span class="sxs-lookup"><span data-stu-id="ad3ae-129">Permission</span></span> |<span data-ttu-id="ad3ae-130">Managed Services 系統管理員</span><span class="sxs-lookup"><span data-stu-id="ad3ae-130">Managed Service Administrator</span></span>  |<span data-ttu-id="ad3ae-131">網站領導</span><span class="sxs-lookup"><span data-stu-id="ad3ae-131">Site Lead</span></span>  |<span data-ttu-id="ad3ae-132">網站技術</span><span class="sxs-lookup"><span data-stu-id="ad3ae-132">Site Tech</span></span>  |
|---------|---------|---------|---------|---------|
|<span data-ttu-id="ad3ae-133">教室</span><span class="sxs-lookup"><span data-stu-id="ad3ae-133">Rooms</span></span>     |<span data-ttu-id="ad3ae-134">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-134">View</span></span>        |<span data-ttu-id="ad3ae-135">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-135">&#10004;</span></span>           |<span data-ttu-id="ad3ae-136">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-136">&#10004;</span></span>           |<span data-ttu-id="ad3ae-137">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-137">&#10004;</span></span>  |
|    |<span data-ttu-id="ad3ae-138">修改</span><span class="sxs-lookup"><span data-stu-id="ad3ae-138">Modify</span></span>         |<span data-ttu-id="ad3ae-139">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-139">&#10004;</span></span>           |<span data-ttu-id="ad3ae-140">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-140">&#10004;</span></span>           |<span data-ttu-id="ad3ae-141">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-141">&#10004;</span></span> |
|    |<span data-ttu-id="ad3ae-142">重設金鑰</span><span class="sxs-lookup"><span data-stu-id="ad3ae-142">Reset key</span></span>         |<span data-ttu-id="ad3ae-143">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-143">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="ad3ae-144">下載金鑰</span><span class="sxs-lookup"><span data-stu-id="ad3ae-144">Download key</span></span>         |<span data-ttu-id="ad3ae-145">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-145">&#10004;</span></span>           |<span data-ttu-id="ad3ae-146">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-146">&#10004;</span></span>          |<span data-ttu-id="ad3ae-147">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-147">&#10004;</span></span> |
|    |<span data-ttu-id="ad3ae-148">取消</span><span class="sxs-lookup"><span data-stu-id="ad3ae-148">Unenroll</span></span>         |<span data-ttu-id="ad3ae-149">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-149">&#10004;</span></span>           |<span data-ttu-id="ad3ae-150">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-150">&#10004;</span></span>           |<span data-ttu-id="ad3ae-151">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-151">&#10004;</span></span> |
|<span data-ttu-id="ad3ae-152">群組管理</span><span class="sxs-lookup"><span data-stu-id="ad3ae-152">Group management</span></span>   |<span data-ttu-id="ad3ae-153">建立</span><span class="sxs-lookup"><span data-stu-id="ad3ae-153">Create</span></span>         |<span data-ttu-id="ad3ae-154">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-154">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="ad3ae-155">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-155">View</span></span>       |<span data-ttu-id="ad3ae-156">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-156">&#10004;</span></span>          |<span data-ttu-id="ad3ae-157">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-157">&#10004;</span></span>           ||
|    |<span data-ttu-id="ad3ae-158">修改</span><span class="sxs-lookup"><span data-stu-id="ad3ae-158">Modify</span></span>         |<span data-ttu-id="ad3ae-159">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-159">&#10004;</span></span>           |           ||
|<span data-ttu-id="ad3ae-160">更新振鈴管理</span><span class="sxs-lookup"><span data-stu-id="ad3ae-160">Update ring management</span></span>    |<span data-ttu-id="ad3ae-161">建立</span><span class="sxs-lookup"><span data-stu-id="ad3ae-161">Create</span></span>         |<span data-ttu-id="ad3ae-162">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-162">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="ad3ae-163">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-163">View</span></span>         |<span data-ttu-id="ad3ae-164">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-164">&#10004;</span></span>           |           ||
|    |<span data-ttu-id="ad3ae-165">修改</span><span class="sxs-lookup"><span data-stu-id="ad3ae-165">Modify</span></span>         |<span data-ttu-id="ad3ae-166">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-166">&#10004;</span></span>           |           ||
|<span data-ttu-id="ad3ae-167">有關</span><span class="sxs-lookup"><span data-stu-id="ad3ae-167">Reports</span></span>   |<span data-ttu-id="ad3ae-168">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-168">View</span></span>        |<span data-ttu-id="ad3ae-169">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-169">&#10004;</span></span>           |<span data-ttu-id="ad3ae-170">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-170">&#10004;</span></span>           ||
|<span data-ttu-id="ad3ae-171">票證管理</span><span class="sxs-lookup"><span data-stu-id="ad3ae-171">Ticket management</span></span>   |<span data-ttu-id="ad3ae-172">建立客戶事件</span><span class="sxs-lookup"><span data-stu-id="ad3ae-172">Create customer incident</span></span>         |<span data-ttu-id="ad3ae-173">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-173">&#10004;</span></span>           |<span data-ttu-id="ad3ae-174">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-174">&#10004;</span></span>           |<span data-ttu-id="ad3ae-175">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-175">&#10004;</span></span>  |
|    |<span data-ttu-id="ad3ae-176">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-176">View</span></span>         |<span data-ttu-id="ad3ae-177">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-177">&#10004;</span></span>           |<span data-ttu-id="ad3ae-178">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-178">&#10004;</span></span>           |<span data-ttu-id="ad3ae-179">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-179">&#10004;</span></span>  |
|    |<span data-ttu-id="ad3ae-180">時更新</span><span class="sxs-lookup"><span data-stu-id="ad3ae-180">Update</span></span>         |<span data-ttu-id="ad3ae-181">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-181">&#10004;</span></span>           |<span data-ttu-id="ad3ae-182">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-182">&#10004;</span></span>           |<span data-ttu-id="ad3ae-183">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-183">&#10004;</span></span>  |
|<span data-ttu-id="ad3ae-184">Microsoft 團隊聊天室 managed services 設定</span><span class="sxs-lookup"><span data-stu-id="ad3ae-184">Microsoft Teams Rooms managed service settings</span></span>    |<span data-ttu-id="ad3ae-185">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-185">View</span></span>         |<span data-ttu-id="ad3ae-186">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-186">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="ad3ae-187">修改</span><span class="sxs-lookup"><span data-stu-id="ad3ae-187">Modify</span></span>        |<span data-ttu-id="ad3ae-188">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-188">&#10004;</span></span>           |         ||
|<span data-ttu-id="ad3ae-189">角色管理</span><span class="sxs-lookup"><span data-stu-id="ad3ae-189">Role management</span></span>    |<span data-ttu-id="ad3ae-190">檢視</span><span class="sxs-lookup"><span data-stu-id="ad3ae-190">View</span></span>         |<span data-ttu-id="ad3ae-191">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-191">&#10004;</span></span>           |         ||
|    |<span data-ttu-id="ad3ae-192">修改</span><span class="sxs-lookup"><span data-stu-id="ad3ae-192">Modify</span></span>         |<span data-ttu-id="ad3ae-193">&#10004;</span><span class="sxs-lookup"><span data-stu-id="ad3ae-193">&#10004;</span></span>           |         ||

## <a name="assign-a-role"></a><span data-ttu-id="ad3ae-194">指派角色</span><span class="sxs-lookup"><span data-stu-id="ad3ae-194">Assign a role</span></span>

<span data-ttu-id="ad3ae-195">若要指派角色，您必須是全域管理員或受管理的服務系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-195">To assign roles, you must be a Global Administrator or Managed Service Administrator.</span></span>

1. <span data-ttu-id="ad3ae-196">在 Microsoft 團隊聊天室 managed 服務入口網站的左側導覽中，移至 [**設定**  >  **角色**]。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-196">In the left navigation of the Microsoft Teams Rooms managed service portal, go to **Settings** > **Roles**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="顯示角色之 [存取控制] 頁面的螢幕擷取畫面":::

2. <span data-ttu-id="ad3ae-198">選取您要指派的角色。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-198">Select the role you want to assign.</span></span>
3. <span data-ttu-id="ad3ae-199">在 [角色] 窗格中，選取 [**作業**  >  **新增**]。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-199">In the role pane, select **Assignments** > **Add**.</span></span>

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="新增角色的 [新增] 選項的螢幕擷取畫面。":::

4. <span data-ttu-id="ad3ae-201">在 [ **一般設定** ] 頁面上的 [ **作業屬性**] 底下，輸入此工作分派的名稱。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-201">On the **General settings** page, under **Assignment properties**, enter a name for this assignment.</span></span> <span data-ttu-id="ad3ae-202">描述是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-202">The description is optional.</span></span> <span data-ttu-id="ad3ae-203">選擇 **[下一步]。**</span><span class="sxs-lookup"><span data-stu-id="ad3ae-203">Choose **Next.**</span></span>
5. <span data-ttu-id="ad3ae-204">在 [ **成員** ] 頁面上，于 [ **搜尋使用者或安全性群組** ] 方塊中，輸入您要授與許可權的租使用者或安全性群組的名稱，然後完成選取專案。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-204">On the **Members** page, in the **Search for user or security group** box, enter the name of a user or security group in your tenant to which you want to give permissions, and then complete the selection.</span></span> <span data-ttu-id="ad3ae-205">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-205">Choose **Next**.</span></span> 
6. <span data-ttu-id="ad3ae-206">在 [ **範圍** ] 頁面上的 [ **搜尋聊天室或聊天室群組** ] 方塊中，輸入可允許使用者管理的聊天室或聊天室群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-206">On the **Scope** page, in the **Search for room or room group** box, type the name of either a room or room group that the user will be allowed to manage.</span></span> <span data-ttu-id="ad3ae-207">選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-207">Choose **Next**.</span></span>
7. <span data-ttu-id="ad3ae-208">在 [ **完成]** 頁面上，查看作業的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-208">On the **Finish** page, review the details of the assignment.</span></span> <span data-ttu-id="ad3ae-209">如果您對設定感到滿意，請選擇 [ **新增作業**]。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-209">If you're satisfied with the configuration, choose **Add assignment**.</span></span> <span data-ttu-id="ad3ae-210">如果您想要編輯節，請使用 [ **上一個** ] 按鈕，或選取左側導覽中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ad3ae-210">If you want to edit a section, use the **Previous** button or select the step in the left navigation.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="ad3ae-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad3ae-211">Related topics</span></span>

- [<span data-ttu-id="ad3ae-212">Microsoft 團隊聊天室管理的服務</span><span class="sxs-lookup"><span data-stu-id="ad3ae-212">Microsoft Teams Rooms managed service</span></span>](microsoft-teams-rooms-premium.md)
