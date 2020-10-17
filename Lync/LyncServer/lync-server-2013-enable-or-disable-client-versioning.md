---
title: Lync Server 2013：啟用或停用用戶端版本設定
description: Lync Server 2013：啟用或停用用戶端版本設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546619"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="570dd-103">啟用或停用 Lync Server 2013 中的用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="570dd-103">Enable or disable client versioning in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="570dd-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="570dd-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="570dd-105">用戶端版本設定可用來開啟或關閉用戶端版本控制，不論是全域性或針對特定網站。</span><span class="sxs-lookup"><span data-stu-id="570dd-105">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="570dd-106">全域用戶端版本設定會以 Lync Server 2013 進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="570dd-106">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="570dd-107">啟用全域設定時，任何已有的用戶端版本原則將會在使用者嘗試登入時生效。</span><span class="sxs-lookup"><span data-stu-id="570dd-107">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="570dd-108">如果您不想要進行任何用戶端版本控制，您可以停用全域用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-108">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="570dd-109">您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，啟用或停用用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-109">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="570dd-110">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="570dd-110">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="570dd-111">使用 Lync Server 控制台啟用或停用用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="570dd-111">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="570dd-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="570dd-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="570dd-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="570dd-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="570dd-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="570dd-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="570dd-115">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本** 設定] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="570dd-115">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="570dd-116">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="570dd-116">Do the following:</span></span>
    
      - <span data-ttu-id="570dd-117">若要全域啟用或停用用戶端版本設定，請按兩下 **全域** 設定，然後修改設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-117">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="570dd-118">若要啟用或停用特定網站的用戶端版本設定，請依序按一下 [ **新增**] 及 [網站]，然後按一下 **[確定]**，然後修改網站的設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-118">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="570dd-119">使用 Windows PowerShell Cmdlet 來啟用或停用用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="570dd-119">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="570dd-120">您可以使用 **Set-CsClientVersionConfiguration** Cmdlet 來啟用或停用用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-120">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="570dd-121">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="570dd-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="570dd-122">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="570dd-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="570dd-123">啟用用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="570dd-123">To enable client versioning</span></span>

  - <span data-ttu-id="570dd-124">您可以設定 **Enabled** 屬性為 True ($True) 來啟用用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-124">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="570dd-125">停用用戶端版本設定</span><span class="sxs-lookup"><span data-stu-id="570dd-125">To disable client versioning</span></span>

  - <span data-ttu-id="570dd-126">您可以將 **Enabled** 屬性設定為 False ($False) ，以停用用戶端版本設定。</span><span class="sxs-lookup"><span data-stu-id="570dd-126">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="570dd-127">如需詳細資訊，請參閱 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="570dd-127">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

