---
title: Lync Server 2013：刪除電話撥入式會議存取號碼
description: Lync Server 2013：刪除電話撥入式會議存取號碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5bed6099f7464884c3bcde8e4ee86ad4207222
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566589"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="f8fe2-103">刪除 Lync Server 2013 中的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-103">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8fe2-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f8fe2-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f8fe2-105">遵循下列步驟，可刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-105">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="f8fe2-106">刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-106">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="f8fe2-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f8fe2-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8fe2-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8fe2-110">在左導覽列中，按一下 [會議]\*\*\*\*，然後按一下 [撥入存取號碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-110">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="f8fe2-111">在頁面中，按一下清單中要刪除的撥入號碼，按一下 **[編輯]**，再按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-111">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f8fe2-112">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f8fe2-113">使用 Windows PowerShell Cmdlet 移除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-113">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f8fe2-114">您可以使用 Windows PowerShell 和 **Remove-CsDialInConferencingAccessNumber** Cmdlet 來刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-114">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="f8fe2-115">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f8fe2-116">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="f8fe2-117">移除特定的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-117">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="f8fe2-118">下列命令會刪除識別碼為 sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="f8fe2-118">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="f8fe2-119">移除指派給特定地區的所有電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-119">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="f8fe2-120">下列命令會刪除與西北地區相關聯的所有電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="f8fe2-120">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="f8fe2-121">移除以主要語言為基礎的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="f8fe2-121">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="f8fe2-122">這個命令會刪除所有以義大利文為主要語言的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="f8fe2-122">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="f8fe2-123">如需詳細資訊，請參閱 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="f8fe2-123">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

