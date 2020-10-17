---
title: Lync Server 2013：啟用或停用同盟協力廠商的探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9fb4e0b243cc1ce9b51deac1c4021f9b3dff56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526820"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="4d56c-102">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="4d56c-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d56c-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d56c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d56c-104">當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="4d56c-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="4d56c-105">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="4d56c-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d56c-106">下列程式假設您已經為組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="4d56c-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="4d56c-107">如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="4d56c-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="4d56c-108">啟用或停用組織的自動探索同盟網域</span><span class="sxs-lookup"><span data-stu-id="4d56c-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="4d56c-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4d56c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d56c-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4d56c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d56c-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4d56c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d56c-112">在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge**設定]。</span><span class="sxs-lookup"><span data-stu-id="4d56c-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4d56c-113">在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4d56c-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4d56c-114">在 [ **編輯 Access Edge**設定] 的 [ **啟用與同盟使用者的通訊**] 下，選取或清除 [ **啟用夥伴網域探索** ] 核取方塊，以啟用或停用自動探索夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="4d56c-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="4d56c-115">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="4d56c-115">Click **Commit**.</span></span>

<span data-ttu-id="4d56c-116">若要讓同盟使用者與 Lync Server 部署中的使用者共同作業，您必須至少設定一個外部存取原則，以支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="4d56c-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="4d56c-117">如需詳細資訊，請參閱部署檔或作業檔中的 [Enable 或 disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。</span><span class="sxs-lookup"><span data-stu-id="4d56c-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4d56c-118">如需控制特定同盟網域存取權的詳細資訊，請參閱在 lync server 2013 中管理組織的 [sip 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、 [在 lync server 2013 中管理組織的 sip 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) ，以及在作業檔中 [管理 LYNC server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 中的 XMPP 同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="4d56c-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d56c-119">使用 Windows PowerShell Cmdlet 來啟用或停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="4d56c-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d56c-120">同盟協力廠商的探索可使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="4d56c-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4d56c-121">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d56c-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d56c-122">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="4d56c-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="4d56c-123">啟用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="4d56c-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="4d56c-124">若要啟用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="4d56c-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="4d56c-125">請注意，您必須啟用 DNS SRV 路由才能變更此屬性值。</span><span class="sxs-lookup"><span data-stu-id="4d56c-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="4d56c-126">停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="4d56c-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="4d56c-127">若要停用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="4d56c-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

