---
title: Lync Server 2013：查看用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f9fa62b16390c490a0ab555559a7895cdce93e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policies-in-lync-server-2013"></a><span data-ttu-id="bcce2-102">在 Lync Server 2013 中查看用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="bcce2-102">View client version policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcce2-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bcce2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bcce2-104">用戶端版本原則是用來全域或針對特定的網站、資料庫池或使用者群組套用一組用戶端版本設定規則。</span><span class="sxs-lookup"><span data-stu-id="bcce2-104">Client version policies are used to apply a set of client versioning rules globally or to a particular site, pool, or group of users.</span></span> <span data-ttu-id="bcce2-105">您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]，查看已在 Lync Server 2013 環境中設定的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="bcce2-105">You can view the client version policies that have been configured in your Lync Server 2013 environment from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="bcce2-106">使用 Lync Server [控制台] 來查看用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="bcce2-106">To view client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bcce2-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bcce2-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bcce2-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bcce2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcce2-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bcce2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bcce2-110">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本原則**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="bcce2-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="bcce2-111">如果您想要查看用戶端版本原則的規則，請在 [**用戶端版本原則**] 頁面上，按兩下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="bcce2-111">If you want to view the rules for a client version policy, on the **Client Version Policy** page, double-click the policy you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bcce2-112">使用 Windows PowerShell Cmdlet 來查看用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="bcce2-112">Viewing Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bcce2-113">您可以使用**CsClientVersionPolicy** Cmdlet 來查看用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="bcce2-113">You can view client version policies by using the **Get-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="bcce2-114">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="bcce2-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bcce2-115">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="bcce2-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policies"></a><span data-ttu-id="bcce2-116">若要查看用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="bcce2-116">To view client version policies</span></span>

  - <span data-ttu-id="bcce2-117">若要查看所有用戶端版本原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="bcce2-117">To view information about all your client version policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicy
    
    <span data-ttu-id="bcce2-118">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="bcce2-118">That will return information similar to this:</span></span>
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

<span data-ttu-id="bcce2-119">如需詳細資訊，請參閱[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bcce2-119">For details, see the Help topic for the [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

