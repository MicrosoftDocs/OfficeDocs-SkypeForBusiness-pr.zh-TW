---
title: 用戶端版本組態
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 除了指定您要在環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端，指定預設動作。 這可讓您限制環境中所使用的用戶端版本，這可協助您控制支援多個用戶端版本的相關成本。
ms.openlocfilehash: 69d8c15688e6afce2f1e92cebc20ad8fb6bc7464
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100649"
---
# <a name="client-version-configuration"></a><span data-ttu-id="ab144-104">用戶端版本組態</span><span class="sxs-lookup"><span data-stu-id="ab144-104">Client Version Configuration</span></span>

<span data-ttu-id="ab144-105">除了指定您要在環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端，指定預設動作。</span><span class="sxs-lookup"><span data-stu-id="ab144-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="ab144-106">這可讓您限制環境中所使用的用戶端版本，這可協助您控制支援多個用戶端版本的相關成本。</span><span class="sxs-lookup"><span data-stu-id="ab144-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ab144-107">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="ab144-107">Tasks you can perform</span></span>

<span data-ttu-id="ab144-108">您可以在「 **用戶端版本** 設定」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="ab144-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="ab144-109">編輯 default ( **Global**) client version configuration。</span><span class="sxs-lookup"><span data-stu-id="ab144-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="ab144-110">為特定網站建立用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="ab144-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="ab144-111">啟用及停用現有的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="ab144-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="ab144-112">由於匿名使用者不會與網站產生關聯，因此匿名使用者只會受到全域層級原則的影響。</span><span class="sxs-lookup"><span data-stu-id="ab144-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ab144-113">UI 參考</span><span class="sxs-lookup"><span data-stu-id="ab144-113">UI Reference</span></span>

<span data-ttu-id="ab144-114">下列清單說明頁面上的功能表、命令、欄位及內容。
</span><span class="sxs-lookup"><span data-stu-id="ab144-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="ab144-115">**新** 您可以為特定網站建立用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="ab144-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="ab144-116">**編輯** 您可以變更任何用戶端版本原則的選項。</span><span class="sxs-lookup"><span data-stu-id="ab144-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="ab144-117">使用此選項，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ab144-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="ab144-118">**顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更用戶端版本設定的選項。</span><span class="sxs-lookup"><span data-stu-id="ab144-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="ab144-119">**全選** 此選項會選取清單中的所有用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="ab144-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="ab144-120">**Delete** 此選項會刪除所有選取的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="ab144-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="ab144-121">**Refresh** 您可以重新整理用戶端版本設定清單，以確認所有用戶端版本設定的選項狀態。</span><span class="sxs-lookup"><span data-stu-id="ab144-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="ab144-122">如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 。</span><span class="sxs-lookup"><span data-stu-id="ab144-122">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="ab144-123">如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)＞。</span><span class="sxs-lookup"><span data-stu-id="ab144-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>