---
title: Lync Server 2013：刪除電話撥入式會議存取號碼
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
ms.openlocfilehash: 50f9bd0929fff858a6e76cc41eccaf2930f0d0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525670"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="12b27-102">刪除 Lync Server 2013 中的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b27-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="12b27-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="12b27-104">遵循下列步驟，可刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="12b27-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="12b27-105">刪除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="12b27-106">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="12b27-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="12b27-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="12b27-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12b27-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="12b27-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12b27-109">在左導覽列中，按一下 [會議]\*\*\*\*，然後按一下 [撥入存取號碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12b27-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="12b27-110">在頁面中，按一下清單中要刪除的撥入號碼，按一下 **[編輯]**，再按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="12b27-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="12b27-111">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="12b27-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="12b27-112">使用 Windows PowerShell Cmdlet 移除電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="12b27-113">您可以使用 Windows PowerShell 和 **Remove-CsDialInConferencingAccessNumber** Cmdlet 來刪除電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="12b27-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="12b27-114">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12b27-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="12b27-115">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="12b27-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="12b27-116">移除特定的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="12b27-117">下列命令會刪除識別碼為 sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="12b27-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="12b27-118">移除指派給特定地區的所有電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="12b27-119">下列命令會刪除與西北地區相關聯的所有電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="12b27-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="12b27-120">移除以主要語言為基礎的電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="12b27-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="12b27-121">這個命令會刪除所有以義大利文為主要語言的電話撥入式會議存取號碼：</span><span class="sxs-lookup"><span data-stu-id="12b27-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="12b27-122">如需詳細資訊，請參閱 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="12b27-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

