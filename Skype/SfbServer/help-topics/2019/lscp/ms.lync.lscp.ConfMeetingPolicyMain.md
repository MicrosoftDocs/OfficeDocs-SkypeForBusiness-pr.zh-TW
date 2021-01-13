---
title: 會議原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 會議原則定義使用者可以在會議中使用的特性與功能。
ms.openlocfilehash: 23377ce4974be1139cf5ff3e7d090cb83d8f2504
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824863"
---
# <a name="conferencing-policy"></a><span data-ttu-id="c701e-103">會議原則</span><span class="sxs-lookup"><span data-stu-id="c701e-103">Conferencing Policy</span></span>

<span data-ttu-id="c701e-104">會議原則定義使用者可以在會議中使用的特性與功能。</span><span class="sxs-lookup"><span data-stu-id="c701e-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="c701e-105">會議原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：</span><span class="sxs-lookup"><span data-stu-id="c701e-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="c701e-106">**全域原則：** 預設會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="c701e-107">您可以編輯全域原則，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="c701e-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="c701e-108">如果您嘗試移除全域原則，則所有設定都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="c701e-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="c701e-109">**網站原則 (選用) ：** 您可以建立一或多個網站會議原則，每個原則都適用于特定網站。</span><span class="sxs-lookup"><span data-stu-id="c701e-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="c701e-110">網站原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="c701e-111">**使用者原則 (選用) ：** 您可以建立一或多個使用者會議原則，每個都適用于特定的使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="c701e-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="c701e-112">使用者原則會覆寫全域原則及網站原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="c701e-113">[ **會議原則** ] 頁面會顯示針對您組織所定義之所有會議原則的清單。</span><span class="sxs-lookup"><span data-stu-id="c701e-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c701e-114">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="c701e-114">Tasks you can perform</span></span>

<span data-ttu-id="c701e-115">您可從「位置原則」頁面執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c701e-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="c701e-116">建立新的網站會議原則或使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="c701e-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="c701e-117">變更全域原則或現有的網站原則或使用者原則</span><span class="sxs-lookup"><span data-stu-id="c701e-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="c701e-118">刪除網站原則或使用者原則</span><span class="sxs-lookup"><span data-stu-id="c701e-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c701e-119">UI 參考</span><span class="sxs-lookup"><span data-stu-id="c701e-119">UI Reference</span></span>

<span data-ttu-id="c701e-120">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="c701e-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c701e-121">**新** 啟動新的網站會議原則或使用者會議原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="c701e-122">**編輯** 開啟選取的會議原則進行編輯、選取清單中的所有會議原則，或刪除選取的網站原則或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c701e-123">**刪除** 會將全域原則的設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="c701e-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="c701e-124">**Refresh** 重新整理會議原則清單。</span><span class="sxs-lookup"><span data-stu-id="c701e-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="c701e-125">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="c701e-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c701e-126">**名稱** 識別會議原則。</span><span class="sxs-lookup"><span data-stu-id="c701e-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="c701e-127">**範圍** 識別會議原則的範圍：全域、網站或使用者。</span><span class="sxs-lookup"><span data-stu-id="c701e-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="c701e-128">**資料** 共同作業檢查會議原則是否指定允許在會議中進行資料協同作業。</span><span class="sxs-lookup"><span data-stu-id="c701e-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="c701e-129">**應用程式共用** 檢查會議原則是否指定允許在會議中進行應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="c701e-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="c701e-130">**音訊** 檢查會議原則是否指定允許在會議中使用音訊。</span><span class="sxs-lookup"><span data-stu-id="c701e-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="c701e-131">**影片** 檢查會議原則是否指定允許在會議中使用影片。</span><span class="sxs-lookup"><span data-stu-id="c701e-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="c701e-132">**PSTN** 檢查會議原則是否指定允許 PSTN 電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="c701e-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="c701e-133">**錄製** 檢查會議原則是否指定允許在會議中錄製。</span><span class="sxs-lookup"><span data-stu-id="c701e-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="c701e-134">如需會議功能及功能的詳細資訊，請參閱規劃檔中的 [會議綜述](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c701e-134">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c701e-135">如需使用會議原則的詳細資訊，請參閱 Operations 檔中的 [會議原則](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c701e-135">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


