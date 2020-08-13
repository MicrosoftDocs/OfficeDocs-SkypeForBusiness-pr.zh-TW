---
title: 建立或修改用戶端版本設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b656b-102">在 Lync Server 2013 中建立或修改用戶端版本設定的集合</span><span class="sxs-lookup"><span data-stu-id="b656b-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b656b-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b656b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b656b-104">用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="b656b-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="b656b-105">全域用戶端版本設定會與 Lync Server 一起安裝，用來啟用或停用整個伺服器部署的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="b656b-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="b656b-106">您也可以設定個別網站的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="b656b-107">您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，建立或修改用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b656b-108">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="b656b-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="b656b-109">使用 Lync Server 控制台建立或修改用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="b656b-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b656b-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b656b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b656b-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b656b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b656b-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b656b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b656b-113">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="b656b-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="b656b-114">在 [**用戶端版本**設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b656b-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="b656b-115">若要建立新的設定，請依序按一下 [**新增**] 及 [網站]，然後按一下 **[確定名稱]** 並更新設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="b656b-116">若要修改設定，請選取設定，按一下 [**編輯**]，再按一下 [**顯示詳細資料**]，然後對設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="b656b-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b656b-117">使用 Windows PowerShell Cmdlet 建立或修改用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="b656b-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b656b-118">您可以使用**set-csclientversionconfiguration** Cmdlet 來建立用戶端版本設定設定，並使用**Set-CsClientVersionConfiguration** Cmdlet 進行修改。</span><span class="sxs-lookup"><span data-stu-id="b656b-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="b656b-119">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b656b-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b656b-120">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="b656b-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="b656b-121">若要建立新的用戶端版本設定的集合</span><span class="sxs-lookup"><span data-stu-id="b656b-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="b656b-122">下列命令會建立套用至 Redmond 網站的新用戶端版本設定的集合。</span><span class="sxs-lookup"><span data-stu-id="b656b-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="b656b-123">在此範例中，會停用 Redmond 網站的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="b656b-124">啟用網站的用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="b656b-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="b656b-125">此命令可啟用 Redmond 網站的用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="b656b-126">停用整個組織中的用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="b656b-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="b656b-127">在此範例中，組織中使用的所有用戶端版本設定均會停用用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="b656b-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="b656b-128">如需詳細資訊，請參閱[set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))和[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b656b-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

