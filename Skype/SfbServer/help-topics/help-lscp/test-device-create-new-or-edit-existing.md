---
title: 測試裝置建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 測試裝置功能與裝置更新功能要一起搭配使用。 您可以將測試裝置新增至「測試裝置」頁面，然後先使用此裝置來確認新更新的功能，再將更新部署至生產裝置。 您可以在全域 (在整個環境中) 測試裝置，或在單一網站內測試裝置。 您是以裝置的媒體存取控制 (MAC) 位址或序號來識別測試裝置。 當您新增裝置時，它會出現在商務用 Skype Server [控制台] 的 [測試裝置] 頁面上的清單中。
ms.openlocfilehash: 56f5c7b43f55f50c5fa5e73cade3f74bea752778
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699460"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="d7f28-107">測試裝置：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="d7f28-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="d7f28-108">測試裝置功能與裝置更新功能要一起搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d7f28-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="d7f28-109">您可以將測試裝置新增至「測試裝置」\*\*\*\* 頁面，然後先使用此裝置來確認新更新的功能，再將更新部署至生產裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f28-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="d7f28-110">您可以在全域 (在整個環境中) 測試裝置，或在單一網站內測試裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f28-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="d7f28-111">您是以裝置的媒體存取控制 (MAC) 位址或序號來識別測試裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f28-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="d7f28-112">當您新增裝置時，它會出現在商務用 Skype Server [控制台] 的 [**測試裝置**] 頁面上的清單中。</span><span class="sxs-lookup"><span data-stu-id="d7f28-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d7f28-113">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="d7f28-113">Tasks you can perform</span></span>

<span data-ttu-id="d7f28-114">您可在「新增測試裝置」\*\*\*\* 或「編輯測試裝置」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="d7f28-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="d7f28-115">新增測試裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f28-115">Add a new test device.</span></span>

- <span data-ttu-id="d7f28-116">修改現有測試裝置的屬性。</span><span class="sxs-lookup"><span data-stu-id="d7f28-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d7f28-117">UI 參考</span><span class="sxs-lookup"><span data-stu-id="d7f28-117">UI Reference</span></span>

<span data-ttu-id="d7f28-118">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="d7f28-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d7f28-119">**範圍**識別測試裝置的範圍（全域或網站）。</span><span class="sxs-lookup"><span data-stu-id="d7f28-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="d7f28-120">**名稱**您可以新增或修改測試裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f28-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d7f28-121">**裝置名稱**您可以新增或修改測試裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="d7f28-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d7f28-122">**識別碼類型**您可以選取下列其中一項來選取要用來識別裝置的方法：</span><span class="sxs-lookup"><span data-stu-id="d7f28-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="d7f28-123">**MAC 位址**</span><span class="sxs-lookup"><span data-stu-id="d7f28-123">**MAC address**</span></span>

  - <span data-ttu-id="d7f28-124">**序號**</span><span class="sxs-lookup"><span data-stu-id="d7f28-124">**Serial number**</span></span>

- <span data-ttu-id="d7f28-125">**唯一識別碼**您可以輸入裝置的 MAC 位址或序列值。</span><span class="sxs-lookup"><span data-stu-id="d7f28-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="d7f28-126">如需測試裝置的詳細資訊，請參閱作業文件中的〈[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="d7f28-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="d7f28-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d7f28-127">See also</span></span>

[<span data-ttu-id="d7f28-128">測試裝置</span><span class="sxs-lookup"><span data-stu-id="d7f28-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="d7f28-129">新-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="d7f28-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="d7f28-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="d7f28-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="d7f28-131">查看貴組織中裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="d7f28-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
