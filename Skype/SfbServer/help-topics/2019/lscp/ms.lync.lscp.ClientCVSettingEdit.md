---
title: 用戶端版本配置建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: 用戶端版本設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會與商務用 Skype Server 一起安裝，並用於針對整個伺服器部署啟用或停用用戶端版本控制。 啟用全域設定時，任何既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。
ms.openlocfilehash: e1146bd9df97320c739eb670200e333e95f4103b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705308"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="c3b1b-106">用戶端版本組態：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="c3b1b-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="c3b1b-107">用戶端版本設定可用來開啟或關閉用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="c3b1b-108">全域用戶端版本設定會與商務用 Skype Server 一起安裝，並用於針對整個伺服器部署啟用或停用用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="c3b1b-109">啟用全域設定時，任何既有的用戶端版本原則都會在使用者嘗試登入時生效。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="c3b1b-110">若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="c3b1b-p103">您也可以建立網站專用的用戶端版本設定，讓您能夠依網站啟用或停用用戶端版本控制。網站專用的設定優先於全域設定。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c3b1b-113">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="c3b1b-113">Tasks you can perform</span></span>

<span data-ttu-id="c3b1b-114">您可以在 [新增用戶端版本設定] \*\*\*\* 或 [編輯用戶端版本設定] \*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c3b1b-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="c3b1b-115">新增或修改用戶端版本設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="c3b1b-116">啟用或停用全域或特定網站的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="c3b1b-117">新增或修改用戶端版本設定的預設動作。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c3b1b-118">UI 參考</span><span class="sxs-lookup"><span data-stu-id="c3b1b-118">UI Reference</span></span>

<span data-ttu-id="c3b1b-119">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="c3b1b-120">**範圍**識別用戶端版本配置的範圍（全域或網站）。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="c3b1b-121">**名稱**您可以新增或修改用戶端版本配置的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="c3b1b-122">**啟用版本控制**您可以在全域或針對網站啟用或停用用戶端版本控制，視設定的範圍而定。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="c3b1b-123">**預設動作**當使用者嘗試使用沒有特定用戶端版本原則的用戶端應用程式登入時，您可以選取要套用的預設動作。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="c3b1b-124">您有下列選項：</span><span class="sxs-lookup"><span data-stu-id="c3b1b-124">You have the following options:</span></span>

  - <span data-ttu-id="c3b1b-125">**允許**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符，則允許用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="c3b1b-126">**封鎖**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符，則可防止用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="c3b1b-127">**使用 URL 的封鎖**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符，就會防止用戶端登入，並包含一則錯誤訊息，其中包含可下載較新用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="c3b1b-128">**允許 URL**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符，則允許用戶端登入，並包含一則錯誤訊息，其中包含可下載較新用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="c3b1b-129">**URL**如果您選取 [封鎖]，並選取 [**以 url**或**允許使用 url**]，您可以指定要包含在錯誤訊息中的用戶端下載 URL。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="c3b1b-130">如需用戶端與用戶端版本之間的互通性詳細資料，請參閱規劃檔中的[用戶端互用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c3b1b-131">如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的〈[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="c3b1b-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

