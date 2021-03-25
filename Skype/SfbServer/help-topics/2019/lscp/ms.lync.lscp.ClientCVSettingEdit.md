---
title: 用戶端版本設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: 用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會以商務用 Skype 伺服器進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。 啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。
ms.openlocfilehash: 67d151a4aaa6ca1e80382977140cbebee2c302ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120282"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="921ec-106">用戶端版本組態：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="921ec-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="921ec-107">用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="921ec-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="921ec-108">全域用戶端版本設定會以商務用 Skype 伺服器進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="921ec-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="921ec-109">啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。</span><span class="sxs-lookup"><span data-stu-id="921ec-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="921ec-110">若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="921ec-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="921ec-p103">您也可以建立網站專用的用戶端版本設定，讓您能夠依網站啟用或停用用戶端版本控制。網站專用的設定優先於全域設定。</span><span class="sxs-lookup"><span data-stu-id="921ec-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="921ec-113">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="921ec-113">Tasks you can perform</span></span>

<span data-ttu-id="921ec-114">您可以在「新的用戶端版本設定」或「編輯用戶端版本設定」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="921ec-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="921ec-115">新增或修改用戶端版本設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="921ec-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="921ec-116">啟用或停用全域或特定網站的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="921ec-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="921ec-117">新增或修改用戶端版本設定的預設動作。</span><span class="sxs-lookup"><span data-stu-id="921ec-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="921ec-118">UI 參考</span><span class="sxs-lookup"><span data-stu-id="921ec-118">UI Reference</span></span>

<span data-ttu-id="921ec-119">下列清單說明頁面上的功能表、命令、欄位及內容。
</span><span class="sxs-lookup"><span data-stu-id="921ec-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="921ec-120">**範圍** 識別用戶端版本設定 (全域或網站) 的範圍。</span><span class="sxs-lookup"><span data-stu-id="921ec-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="921ec-121">**名稱** 您可以新增或修改用戶端版本設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="921ec-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="921ec-122">**啟用版本控制** 您可以啟用或停用全域或網站的用戶端版本控制，視設定的範圍而定。</span><span class="sxs-lookup"><span data-stu-id="921ec-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="921ec-123">**預設動作** 您可以選取當使用者嘗試使用沒有特定用戶端版本原則的用戶端應用程式登入時，將會套用的預設動作。</span><span class="sxs-lookup"><span data-stu-id="921ec-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="921ec-124">您有下列選項：</span><span class="sxs-lookup"><span data-stu-id="921ec-124">You have the following options:</span></span>

  - <span data-ttu-id="921ec-125">**允許** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，允許用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="921ec-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="921ec-126">**封鎖** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，禁止用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="921ec-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="921ec-127">**使用 URL 的封鎖** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，禁止用戶端登入，並包含錯誤訊息，其中包含可下載更新的用戶端 URL。</span><span class="sxs-lookup"><span data-stu-id="921ec-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="921ec-128">**允許搭配 URL** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，允許用戶端登入，並包含包含 URL 的錯誤訊息，可供下載更新的用戶端。</span><span class="sxs-lookup"><span data-stu-id="921ec-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="921ec-129">**URL** 如果您選取 [ **封鎖 WITH url** ] 或 [ **允許搭配 url**]，您可以指定要包含在錯誤訊息中的用戶端下載 URL。</span><span class="sxs-lookup"><span data-stu-id="921ec-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="921ec-130">如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 。</span><span class="sxs-lookup"><span data-stu-id="921ec-130">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="921ec-131">如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)＞。</span><span class="sxs-lookup"><span data-stu-id="921ec-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>