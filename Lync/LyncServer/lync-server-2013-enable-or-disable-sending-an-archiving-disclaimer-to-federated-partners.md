---
title: 啟用或停用傳送封存免責聲明至同盟合作夥伴的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9364f3562c837b949ef589fc7c5cbd2bc4a2b4cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="4116c-102">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</span><span class="sxs-lookup"><span data-stu-id="4116c-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4116c-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4116c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4116c-104">在您部署您的 Edge 伺服器並為貴組織啟用同盟後，您應該已指定是否要將封存免責聲明自動傳送給聯盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="4116c-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="4116c-105">如果您封存外部通訊，您應該啟用傳送封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="4116c-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="4116c-106">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="4116c-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4116c-107">下列程式假設您已經為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="4116c-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="4116c-108">如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="4116c-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="4116c-109">啟用或停用將封存免責聲明傳送給聯盟夥伴</span><span class="sxs-lookup"><span data-stu-id="4116c-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="4116c-110">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4116c-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4116c-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4116c-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4116c-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4116c-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4116c-113">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="4116c-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4116c-114">按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4116c-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4116c-115">在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊，以啟用或停用自動傳送封存免責聲明。</span><span class="sxs-lookup"><span data-stu-id="4116c-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="4116c-116">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4116c-116">Click **Commit**.</span></span>

<span data-ttu-id="4116c-117">若要讓聯盟使用者在 Lync Server 2013 部署中與使用者共同作業，您必須至少已將一個外部存取原則設定為支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="4116c-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="4116c-118">如需詳細資訊，請參閱在部署檔或作業檔中[管理 Lync Server 2013 中的 XMPP 聯盟合作夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="4116c-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4116c-119">如需控制特定聯盟網域存取權的詳細資料，請參閱在部署檔或操作檔中[設定 Lync Server 2013 允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="4116c-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4116c-120">使用 Windows PowerShell Cmdlet 來啟用或停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="4116c-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4116c-121">您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理存檔免責聲明的使用。</span><span class="sxs-lookup"><span data-stu-id="4116c-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4116c-122">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="4116c-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4116c-123">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="4116c-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="4116c-124">啟用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="4116c-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="4116c-125">若要啟用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="4116c-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="4116c-126">停用封存放棄免責聲明</span><span class="sxs-lookup"><span data-stu-id="4116c-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="4116c-127">若要停用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="4116c-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

