---
title: Lync Server 2013： View client version configuration 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec472bff967bc2a8ffb75d09e3515654487be41
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506600"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e2391-102">在 Lync Server 2013 中查看用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="e2391-102">View client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2391-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e2391-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e2391-104">用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="e2391-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="e2391-105">全域用戶端版本設定會以 Lync Server 2013 進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。</span><span class="sxs-lookup"><span data-stu-id="e2391-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="e2391-106">啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。</span><span class="sxs-lookup"><span data-stu-id="e2391-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="e2391-107">您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，查看用戶端版本設定設定。</span><span class="sxs-lookup"><span data-stu-id="e2391-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2391-108">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="e2391-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e2391-109">使用 Lync Server 控制台查看用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="e2391-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e2391-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e2391-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2391-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e2391-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2391-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e2391-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2391-113">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本** 設定] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="e2391-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e2391-114">按兩下您要查看之用戶端版本設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="e2391-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2391-115">使用 Windows PowerShell Cmdlet 來查看用戶端版本設定設定</span><span class="sxs-lookup"><span data-stu-id="e2391-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2391-116">您可以使用 **Get-CsClientVersionConfiguration** Cmdlet 來查看用戶端版本設定設定。</span><span class="sxs-lookup"><span data-stu-id="e2391-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="e2391-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2391-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e2391-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e2391-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="e2391-119">若要查看用戶端版本設定資訊</span><span class="sxs-lookup"><span data-stu-id="e2391-119">To view client version configuration information</span></span>

  - <span data-ttu-id="e2391-120">若要查看所有用戶端版本設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e2391-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="e2391-121">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="e2391-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="e2391-122">如需詳細資訊，請參閱 [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="e2391-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

