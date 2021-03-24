---
title: 測試裝置建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: 測試裝置功能會搭配裝置更新功能一起運作。 您可以將測試裝置新增至 [測試裝置] 頁面，然後使用此裝置來確認新更新的功能，再將更新部署至實際執行裝置。 您可以在整個環境) 或單一網站內，測試裝置全域 (。 您可以透過媒體存取控制來識別測試裝置 (MAC) 位址或序號。 當您新增裝置時，它會顯示在商務用 Skype Server [控制台] 的 [測試裝置] 頁面上的清單中。
ms.openlocfilehash: 959abca17e208a397cbdd9ad6a69ba241aad4362
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100629"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="28779-107">測試裝置：建立新的或編輯現有裝置</span><span class="sxs-lookup"><span data-stu-id="28779-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="28779-108">測試裝置功能會搭配裝置更新功能一起運作。</span><span class="sxs-lookup"><span data-stu-id="28779-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="28779-109">您可以將測試裝置新增至 [ **測試裝置** ] 頁面，然後使用此裝置來確認新更新的功能，再將更新部署至實際執行裝置。</span><span class="sxs-lookup"><span data-stu-id="28779-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="28779-110">您可以在整個環境) 或單一網站內，測試裝置全域 (。</span><span class="sxs-lookup"><span data-stu-id="28779-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="28779-111">您可以透過媒體存取控制來識別測試裝置 (MAC) 位址或序號。</span><span class="sxs-lookup"><span data-stu-id="28779-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="28779-112">當您新增裝置時，它會顯示在商務用 Skype Server [控制台] 的 [ **測試裝置** ] 頁面上的清單中。</span><span class="sxs-lookup"><span data-stu-id="28779-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="28779-113">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="28779-113">Tasks you can perform</span></span>

<span data-ttu-id="28779-114">您可以在「 **新增測試裝置** 」或「 **編輯測試裝置** 」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="28779-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="28779-115">新增測試裝置。</span><span class="sxs-lookup"><span data-stu-id="28779-115">Add a new test device.</span></span>

- <span data-ttu-id="28779-116">修改現有測試裝置的屬性。</span><span class="sxs-lookup"><span data-stu-id="28779-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="28779-117">UI 參考</span><span class="sxs-lookup"><span data-stu-id="28779-117">UI Reference</span></span>

<span data-ttu-id="28779-118">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="28779-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="28779-119">**範圍** 識別測試裝置的範圍 (全域或網站) 。</span><span class="sxs-lookup"><span data-stu-id="28779-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="28779-120">**名稱** 您可以新增或修改測試裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="28779-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="28779-121">**裝置名稱** 您可以新增或修改測試裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="28779-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="28779-122">**識別碼類型** 您可以選取下列其中一項，以選取用來識別裝置的方法：</span><span class="sxs-lookup"><span data-stu-id="28779-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="28779-123">**MAC 位址**</span><span class="sxs-lookup"><span data-stu-id="28779-123">**MAC address**</span></span>

  - <span data-ttu-id="28779-124">**序號**</span><span class="sxs-lookup"><span data-stu-id="28779-124">**Serial number**</span></span>

- <span data-ttu-id="28779-125">**唯一識別碼** 您可以輸入裝置的 MAC 位址或序號。</span><span class="sxs-lookup"><span data-stu-id="28779-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="28779-126">如需測試裝置的詳細資訊，請參閱 Operations 檔中的 [Add a Device To Test Update 功能性](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) 。</span><span class="sxs-lookup"><span data-stu-id="28779-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="28779-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28779-127">See also</span></span>

[<span data-ttu-id="28779-128">測試裝置</span><span class="sxs-lookup"><span data-stu-id="28779-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="28779-129">新 CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="28779-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="28779-130">CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="28779-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="28779-131">查看您組織中裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="28779-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)