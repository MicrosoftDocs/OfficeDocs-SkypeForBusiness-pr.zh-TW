---
title: Lync Server 2013：重設外部使用者存取的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="7c04b-102">在 Lync Server 2013 中重設外部使用者存取的全域原則</span><span class="sxs-lookup"><span data-stu-id="7c04b-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c04b-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7c04b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7c04b-104">您無法完全刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="7c04b-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="7c04b-105">在全域原則上使用 [**刪除**] 選項時，只會將全域原則重設為預設設定，而不包含任何外部使用者存取選項的支援。</span><span class="sxs-lookup"><span data-stu-id="7c04b-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="7c04b-106">將全域原則重設為預設設定</span><span class="sxs-lookup"><span data-stu-id="7c04b-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="7c04b-107">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7c04b-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7c04b-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7c04b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7c04b-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c04b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7c04b-110">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="7c04b-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7c04b-111">在 [**外部存取原則**] 索引標籤上，按一下 [全域原則]，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="7c04b-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="7c04b-112">當系統提示您確認刪除時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7c04b-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="7c04b-113">頁面頂端會出現一則訊息，通知您全域原則已重設。</span><span class="sxs-lookup"><span data-stu-id="7c04b-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7c04b-114">使用 Windows PowerShell Cmdlet 來重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="7c04b-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7c04b-115">您可以使用 Windows PowerShell 和 CsExternalAccessPolicy Cmdlet 來重設全域外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="7c04b-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="7c04b-116">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="7c04b-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="7c04b-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="7c04b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="7c04b-118">若要重設全域外部存取原則</span><span class="sxs-lookup"><span data-stu-id="7c04b-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="7c04b-119">這個命令會重定全域外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="7c04b-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="7c04b-120">如需詳細資訊，請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="7c04b-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

