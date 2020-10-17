---
title: Lync Server 2013：刪除現有的註冊機配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0624806ba8ed2f10bc0c7cffbf1e8879209c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525600"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="cb2ef-102">在 Lync Server 2013 中刪除現有的註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb2ef-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cb2ef-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cb2ef-104">請遵循下列步驟來刪除註冊機。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="cb2ef-105">若要刪除註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="cb2ef-106">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cb2ef-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb2ef-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb2ef-109">在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="cb2ef-110">在 [ **註冊機** ] 頁面上的搜尋欄位中，輸入您要刪除之註冊機構的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="cb2ef-111">在清單中，按一下您想要的註冊機構，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="cb2ef-112">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb2ef-113">使用 Windows PowerShell Cmdlet 移除註冊機設定設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cb2ef-114">您可以使用 Windows PowerShell 和 **set-csproxyconfiguration** Cmdlet 來刪除註冊機設定設定。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="cb2ef-115">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb2ef-116">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="cb2ef-117">移除一組特定的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="cb2ef-118">下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機安全性設定：</span><span class="sxs-lookup"><span data-stu-id="cb2ef-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="cb2ef-119">若要移除所有套用至網站範圍的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="cb2ef-120">下列命令會移除所有已套用至註冊機構服務的註冊機安全性設定：</span><span class="sxs-lookup"><span data-stu-id="cb2ef-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="cb2ef-121">移除所有允許 NTLM 驗證的註冊機構安全性設定</span><span class="sxs-lookup"><span data-stu-id="cb2ef-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="cb2ef-122">下列命令會刪除所有的註冊器安全性設定，這些設定允許使用 NTLM 進行用戶端驗證：</span><span class="sxs-lookup"><span data-stu-id="cb2ef-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="cb2ef-123">如需詳細資訊，請參閱 [Remove-set-csproxyconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="cb2ef-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

