---
title: Lync Server 2013： View PIN 原則資訊
description: Lync Server 2013： View PIN 原則資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d60125663bed2b79921de62663865c56b6a27786
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579639"
---
# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="ad201-103">在 Lync Server 2013 中查看 PIN 原則資訊</span><span class="sxs-lookup"><span data-stu-id="ad201-103">View PIN policy inforrmation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad201-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ad201-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ad201-105">您可以使用 [ **PIN 原則** ] 索引標籤來查看使用 IP 電話連線至 Lync 2013 之使用者的個人身分識別號碼 (PIN) 驗證。</span><span class="sxs-lookup"><span data-stu-id="ad201-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="ad201-106">若要使用 PIN 驗證，請確定已在 Web 服務設定中選取了 [啟用 PIN 驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad201-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="ad201-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中修改現有的 Web 服務設定](lync-server-2013-modify-existing-web-service-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ad201-107">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="ad201-108">請遵循下列步驟來修改使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="ad201-108">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="ad201-109">在 Lync Server 控制台中查看 PIN 原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="ad201-109">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ad201-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ad201-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ad201-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ad201-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad201-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ad201-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ad201-113">在左導覽列中，依序按一下 [安全性]\*\*\*\* 和 [PIN 原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad201-113">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="ad201-114">在「PIN 原則」\*\*\*\* 頁面上，依序按一下原則、[編輯]\*\*\*\* 和 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad201-114">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ad201-115">使用 Windows PowerShell Cmdlet 來查看 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="ad201-115">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ad201-116">您也可以使用 Windows PowerShell 和 Get-CsPinPolicy Cmdlet 來查看 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="ad201-116">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="ad201-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad201-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ad201-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="ad201-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="ad201-119">若要查看 PIN 碼原則</span><span class="sxs-lookup"><span data-stu-id="ad201-119">To view PIN policies</span></span>

  - <span data-ttu-id="ad201-120">若要查看所有 PIN 原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="ad201-120">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="ad201-121">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="ad201-121">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="ad201-122">如需詳細資訊，請參閱 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="ad201-122">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad201-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ad201-123">See Also</span></span>


[<span data-ttu-id="ad201-124">在 Lync Server 2013 中修改現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="ad201-124">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="ad201-125">在 Lync Server 2013 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="ad201-125">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

