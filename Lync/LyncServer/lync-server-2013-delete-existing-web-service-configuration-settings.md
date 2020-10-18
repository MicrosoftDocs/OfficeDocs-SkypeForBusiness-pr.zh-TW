---
title: Lync Server 2013：刪除現有的 Web 服務設定
description: Lync Server 2013：刪除現有的 Web 服務設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a28197f26a447112e29b6e4a831585dd49a9854
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575849"
---
# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="61cb3-103">在 Lync Server 2013 中刪除現有的 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="61cb3-103">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61cb3-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="61cb3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="61cb3-105">請遵循下列步驟刪除 web 服務設定。</span><span class="sxs-lookup"><span data-stu-id="61cb3-105">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="61cb3-106">若要刪除 web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="61cb3-106">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="61cb3-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="61cb3-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="61cb3-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="61cb3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61cb3-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="61cb3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61cb3-110">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="61cb3-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="61cb3-111">在 [ **Web 服務** ] 頁面上的搜尋欄位中，輸入您要刪除之原則的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="61cb3-111">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="61cb3-112">在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="61cb3-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="61cb3-113">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="61cb3-113">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="61cb3-114">使用 Windows PowerShell Cmdlet 刪除 Web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="61cb3-114">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="61cb3-115">您可以使用 Windows PowerShell 和 **Remove-CsWebServiceConfiguration** Cmdlet 刪除 web 服務設定設定。</span><span class="sxs-lookup"><span data-stu-id="61cb3-115">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="61cb3-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61cb3-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="61cb3-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="61cb3-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="61cb3-118">刪除特定的 web 服務設定集合集合</span><span class="sxs-lookup"><span data-stu-id="61cb3-118">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="61cb3-119">下列命令會移除套用至 Redmond 網站的 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="61cb3-119">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="61cb3-120">若要刪除所有套用至網站範圍的 web 服務設定設定</span><span class="sxs-lookup"><span data-stu-id="61cb3-120">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="61cb3-121">下列命令會移除套用至服務範圍的所有 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="61cb3-121">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="61cb3-122">若要刪除所有允許憑證驗證的 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="61cb3-122">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="61cb3-123">下列命令會移除所有允許使用憑證驗證的 Web 服務安全性設定：</span><span class="sxs-lookup"><span data-stu-id="61cb3-123">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="61cb3-124">如需詳細資訊，請參閱 [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="61cb3-124">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61cb3-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61cb3-125">See Also</span></span>


[<span data-ttu-id="61cb3-126">在 Lync Server 2013 控制台中設定驗證</span><span class="sxs-lookup"><span data-stu-id="61cb3-126">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

