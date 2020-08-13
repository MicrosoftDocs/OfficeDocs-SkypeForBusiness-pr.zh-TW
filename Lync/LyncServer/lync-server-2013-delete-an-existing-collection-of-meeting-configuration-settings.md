---
title: 刪除現有的會議配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971bde33feee35d91c0cbefe0fea931533818862
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="63041-102">在 Lync Server 2013 中刪除現有的會議配置設定集合</span><span class="sxs-lookup"><span data-stu-id="63041-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63041-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="63041-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="63041-104">您可以刪除網站或使用者設定。</span><span class="sxs-lookup"><span data-stu-id="63041-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="63041-105">無法移除全域設定。</span><span class="sxs-lookup"><span data-stu-id="63041-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="63041-106">如果您刪除全域設定，它會自動重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="63041-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="63041-107">刪除網站或使用者會議設定</span><span class="sxs-lookup"><span data-stu-id="63041-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="63041-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="63041-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63041-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="63041-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63041-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="63041-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63041-111">在左導覽列中，按一下 [**會議**]，然後按一下 [**會議**設定]。</span><span class="sxs-lookup"><span data-stu-id="63041-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="63041-112">在會議設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [**編輯**]，再按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="63041-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="63041-113">使用 Windows PowerShell Cmdlet 移除會議配置設定</span><span class="sxs-lookup"><span data-stu-id="63041-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="63041-114">您可以使用 Windows PowerShell 和 Remove-CsMeetingConfiguration Cmdlet 來刪除會議設定。</span><span class="sxs-lookup"><span data-stu-id="63041-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="63041-115">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63041-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="63041-116">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="63041-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="63041-117">移除指定的會議配置設定集合</span><span class="sxs-lookup"><span data-stu-id="63041-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="63041-118">此命令會移除套用至 Redmond 網站的會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="63041-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="63041-119">移除套用至網站範圍的所有會議設定</span><span class="sxs-lookup"><span data-stu-id="63041-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="63041-120">此命令會移除所有套用至網站範圍的會議設定：</span><span class="sxs-lookup"><span data-stu-id="63041-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="63041-121">若要移除預設會承認匿名使用者的所有會議設定設定</span><span class="sxs-lookup"><span data-stu-id="63041-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="63041-122">而且這一項會移除所有允許匿名使用者預設承認的設定：</span><span class="sxs-lookup"><span data-stu-id="63041-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="63041-123">如需詳細資訊，請參閱[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="63041-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

