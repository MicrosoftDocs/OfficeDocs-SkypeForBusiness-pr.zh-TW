---
title: Lync Server 2013：啟用或停用探索同盟協力廠商
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="3deb0-102">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="3deb0-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3deb0-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3deb0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3deb0-104">當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="3deb0-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="3deb0-105">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="3deb0-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3deb0-106">下列程式假設您已經為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="3deb0-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="3deb0-107">如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="3deb0-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="3deb0-108">若要啟用或停用貴組織的聯盟網域自動探索</span><span class="sxs-lookup"><span data-stu-id="3deb0-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="3deb0-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3deb0-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3deb0-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3deb0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3deb0-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3deb0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3deb0-112">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="3deb0-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3deb0-113">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="3deb0-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3deb0-114">在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**啟用合作夥伴網域探索**] 核取方塊，以啟用或停用合作夥伴網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="3deb0-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="3deb0-115">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3deb0-115">Click **Commit**.</span></span>

<span data-ttu-id="3deb0-116">若要讓聯盟使用者在 Lync Server 部署中與使用者共同作業，您也必須至少已設定一個外部存取原則來支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3deb0-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="3deb0-117">如需詳細資訊，請參閱在部署檔或操作檔中[啟用或停用 Lync Server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="3deb0-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="3deb0-118">如需控制特定聯盟網域存取權的詳細資料，請參閱在 lync server [2013 中管理貴組織的 sip 聯盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、在[lync server 2013 中管理貴組織的 sip 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)，以及在 Operations 檔中管理[LYNC server 2013 中的 XMPP 聯盟合作夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="3deb0-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3deb0-119">使用 Windows PowerShell Cmdlet 來啟用或停用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="3deb0-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3deb0-120">同盟合作夥伴的探索可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 進行管理。</span><span class="sxs-lookup"><span data-stu-id="3deb0-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3deb0-121">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="3deb0-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3deb0-122">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="3deb0-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="3deb0-123">若要啟用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="3deb0-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="3deb0-124">若要啟用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="3deb0-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="3deb0-125">請注意，您必須啟用 DNS SRV 路由才能變更這個屬性值。</span><span class="sxs-lookup"><span data-stu-id="3deb0-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="3deb0-126">若要停用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="3deb0-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="3deb0-127">若要停用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="3deb0-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

