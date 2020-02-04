---
title: Enterprise Voice 的安全性和組態先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="cc385-102">Lync Server 2013 中的企業語音安全性與設定先決條件</span><span class="sxs-lookup"><span data-stu-id="cc385-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc385-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cc385-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cc385-104">確認您的基礎結構符合下列安全性、使用者配置和案例特定的硬體先決條件。</span><span class="sxs-lookup"><span data-stu-id="cc385-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="cc385-105">管理許可權與證書基礎結構</span><span class="sxs-lookup"><span data-stu-id="cc385-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="cc385-106">請確定您的環境已使用下列管理使用者群組和證書基礎結構加以設定，以便在企業語音部署程式中使用。</span><span class="sxs-lookup"><span data-stu-id="cc385-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="cc385-107">部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cc385-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="cc385-108">執行設定任務的系統管理員必須具備足夠的許可權：</span><span class="sxs-lookup"><span data-stu-id="cc385-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="cc385-109">**CsVoiceAdministrator：** 這個系統管理員角色可以執行語音設定工作、管理語音應用程式，以及將語音原則指派給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="cc385-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="cc385-110">**CsUserAdministrator：** 這個系統管理員角色可以管理使用者屬性，例如為使用者啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="cc385-110">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="cc385-111">除了封存原則之外，此管理員角色還可以指派每個使用者的原則;移動使用者;以及管理常見的區域電話和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="cc385-111">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="cc385-112">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="cc385-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cc385-113">委派能讓更多的系統管理員參與您的 Lync Server 部署，而不需要開啟對資源的不必要存取權。</span><span class="sxs-lookup"><span data-stu-id="cc385-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="cc385-114">管理的金鑰結構（MKI）是透過 Microsoft 或協力廠商憑證授權單位（CA）基礎結構來部署和設定。</span><span class="sxs-lookup"><span data-stu-id="cc385-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cc385-115">如需有關 Lync Server 中證書需求的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 證書基礎結構需求</A>。</span><span class="sxs-lookup"><span data-stu-id="cc385-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="cc385-116">使用者設定</span><span class="sxs-lookup"><span data-stu-id="cc385-116">User Configuration</span></span>

<span data-ttu-id="cc385-117">如果您在前端部署期間 collocated 每個前端池或標準版伺服器的中繼伺服器，則在安裝這些伺服器角色的檔案期間，系統會自動設定企業語音所需的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="cc385-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="cc385-118">如果您目前正在新部署企業語音工作負載，請在開始進行部署程式之前，為您打算啟用企業語音的每位使用者指定主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cc385-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="cc385-119">身為管理員，您必須負責確保此號碼是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cc385-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="cc385-120">在實施前，所有的主要電話號碼都必須經過標準化（正確格式化），並使用 Lync Server [控制台] 複製到每個使用者的**行 URI**屬性。</span><span class="sxs-lookup"><span data-stu-id="cc385-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cc385-121">如需企業語音部署所需的主要電話號碼範例，請參閱規劃檔中的 lync server <A href="lync-server-2013-dial-plans-and-normalization-rules.md">2013</A>中的 [lync server 2013] 區段中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">撥號方案與正常化規則</A>。</span><span class="sxs-lookup"><span data-stu-id="cc385-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="cc385-122">後續步驟：安裝檔案或設定 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="cc385-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="cc385-123">在驗證企業語音的軟體與環境先決條件之後，您可以使用下列內容來執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="cc385-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="cc385-124">安裝中繼伺服器，如在[Lync server 2013 中安裝用於進行轉送服務伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案中所述，但僅限您想要部署獨立的中繼伺服器或池，因為在 collocated 時，會將轉送伺服器安裝為前端池或標準版伺服器部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc385-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="cc385-125">或者，開始設定設定以傳送企業語音使用者的呼叫，如在[Lync Server 2013 中設定 trunks 中](lync-server-2013-configuring-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="cc385-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

