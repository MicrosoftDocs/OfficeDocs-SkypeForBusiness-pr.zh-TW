---
title: 會議組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: '[會議設定設定] 定義使用者可以建立的會議類型（也就是 calledmeetings），並控制匿名使用者和電話撥入式會議使用者可以加入這些會議的方式（或是否有）。 這些設定僅適用于排程的會議。 它們不適用於在用戶端中按一下 [立即開會] 選項所建立的即席會議。'
ms.openlocfilehash: e237e9c5122547338f9ea33848a22b87fabce368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822676"
---
# <a name="meeting-configuration"></a><span data-ttu-id="d8e11-105">會議組態</span><span class="sxs-lookup"><span data-stu-id="d8e11-105">Meeting Configuration</span></span>

<span data-ttu-id="d8e11-p102">會議組態設定定義使用者所能建立的會議類型，並控制匿名使用者與電話撥入式會議使用者是否可以加入這些會議及其加入方式。這些設定僅適用於排程的會議，而不適用於透過按一下在用戶端中的 [立即開會] 選項所建立的臨時會議。</span><span class="sxs-lookup"><span data-stu-id="d8e11-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="d8e11-109">會議設定會套用在全域、網站或集區層級：</span><span class="sxs-lookup"><span data-stu-id="d8e11-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="d8e11-110">**全域會議設定：** 預設會建立全域會議設定。</span><span class="sxs-lookup"><span data-stu-id="d8e11-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="d8e11-111">您只可編輯全域會議設定，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="d8e11-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="d8e11-112">如果您嘗試移除全域會議設定，所有設定皆會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d8e11-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="d8e11-113">**網站會議配置（選用）：** 您可以建立一或多個網站會議設定，每個設定都適用于特定網站。</span><span class="sxs-lookup"><span data-stu-id="d8e11-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="d8e11-114">網站設定優先於全域設定。</span><span class="sxs-lookup"><span data-stu-id="d8e11-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="d8e11-115">**[泳池會議設定] （選用）：** 您可以建立一個或多個 [池會議] 設定，每個設定都適用于特定的文件庫。</span><span class="sxs-lookup"><span data-stu-id="d8e11-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="d8e11-116">集區設定優先於全域設定和網站設定。</span><span class="sxs-lookup"><span data-stu-id="d8e11-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="d8e11-117">「會議設定」\*\*\*\* 頁面會顯示針對組織所定義的所有會議設定的清單。</span><span class="sxs-lookup"><span data-stu-id="d8e11-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d8e11-118">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="d8e11-118">Tasks you can perform</span></span>

<span data-ttu-id="d8e11-119">您可以在「會議設定」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="d8e11-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="d8e11-120">建立新的網站會議設定或集區會議設定</span><span class="sxs-lookup"><span data-stu-id="d8e11-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="d8e11-121">變更全域設定或現有的網站設定或集區設定</span><span class="sxs-lookup"><span data-stu-id="d8e11-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="d8e11-122">刪除網站設定或集區設定</span><span class="sxs-lookup"><span data-stu-id="d8e11-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d8e11-123">UI 參考</span><span class="sxs-lookup"><span data-stu-id="d8e11-123">UI Reference</span></span>

<span data-ttu-id="d8e11-124">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="d8e11-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="d8e11-125">**新增**啟動新的網站會議設定或 [池會議] 設定。</span><span class="sxs-lookup"><span data-stu-id="d8e11-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="d8e11-126">[**編輯**]開啟選取的會議設定以進行編輯、選取清單中的所有會議設定，或刪除選取的網站設定或文件庫設定。</span><span class="sxs-lookup"><span data-stu-id="d8e11-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8e11-127">**刪除** 會將全域會議設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d8e11-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="d8e11-128">**更新**刷新會議配置清單。</span><span class="sxs-lookup"><span data-stu-id="d8e11-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="d8e11-129">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="d8e11-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d8e11-130">**名稱**識別會議配置。</span><span class="sxs-lookup"><span data-stu-id="d8e11-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="d8e11-131">**範圍**識別會議設定的範圍： [全域]、[網站] 或 [文件庫]。</span><span class="sxs-lookup"><span data-stu-id="d8e11-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="d8e11-132">如需使用會議設定的詳細資訊，請參閱作業文件中的〈[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="d8e11-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


