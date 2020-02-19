---
title: Lync Server 2013： 檢視狀態的樹系的通用設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ce07a106e583f3ea0d4b523e1cf882677c19b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="37ae1-102">檢視狀態的 Lync Server 2013 中的樹系的全域設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ae1-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="37ae1-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="37ae1-104">系統管理員應該檢閱每月的 Lync Server 2013 部署的全域設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="37ae1-105">目標是將檢閱實作的設定對一組已知的設定 — 基準組態，以協助確保設定均有效，並判斷是否應更新文件的基準。</span><span class="sxs-lookup"><span data-stu-id="37ae1-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="37ae1-106">變更全域設定應該實作透過應該包含記載的新設定的變更控制程序。</span><span class="sxs-lookup"><span data-stu-id="37ae1-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="37ae1-107">下列各節將說明應檢閱的全域設定：</span><span class="sxs-lookup"><span data-stu-id="37ae1-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="37ae1-108">檢查一般設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-108">Check general settings</span></span>

<span data-ttu-id="37ae1-109">檢查一般設定，包括針對 Lync Server 2013 支援的工作階段初始通訊協定 (SIP) 網域。</span><span class="sxs-lookup"><span data-stu-id="37ae1-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="37ae1-110">使用 Windows PowerShell 和**Get-cssipdomain**指令程式，可以傳回 SIP 網域資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="37ae1-111">若要傳回這項資訊，請執行`Get-CsSipDomain`Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="37ae1-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="37ae1-112">Get-cssipdomain 會傳回類似的所有授權的 SIP 網域的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="37ae1-113">Identity 名稱 IsDefault</span><span class="sxs-lookup"><span data-stu-id="37ae1-113">Identity Name IsDefault</span></span>

<span data-ttu-id="37ae1-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="37ae1-114">\-------- ---- ---------</span></span>

<span data-ttu-id="37ae1-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="37ae1-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="37ae1-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="37ae1-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="37ae1-117">如果的 IsDefault 屬性設為 True，對應的網域就會是預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="37ae1-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="37ae1-118">您可以使用 Set CsSipDomain 指令程式來變更預設 SIP 網域，為您的組織。</span><span class="sxs-lookup"><span data-stu-id="37ae1-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="37ae1-119">不過，您只是無法刪除預設 SIP 網域，因為這樣會讓您沒有預設網域。</span><span class="sxs-lookup"><span data-stu-id="37ae1-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="37ae1-120">如果您想要刪除 fabrikam.com 網域 （如上述範例所示），您必須先設定 na.fabrikam.com 設為預設網域。</span><span class="sxs-lookup"><span data-stu-id="37ae1-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="37ae1-121">請檢查會議設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-121">Check meeting settings</span></span>

<span data-ttu-id="37ae1-122">會議的設定包括會議原則定義，並參與會議的匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="37ae1-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="37ae1-123">使用 Windows PowerShell 和**Get-csmeetingconfiguration** cmdlet 可以擷取會議組態設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="37ae1-124">例如，此命令會傳回的資訊將全域會議組態設定：</span><span class="sxs-lookup"><span data-stu-id="37ae1-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="37ae1-125">Get-csmeetingconfiguration – Identity"Global"會議組態設定也可以在網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="37ae1-126">因此，您可能想要使用下列命令，它會傳回所有會議的相關資訊的組態設定：</span><span class="sxs-lookup"><span data-stu-id="37ae1-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="37ae1-127">**Get-csmeetingconfiguration** cmdlet 會傳回類似下列資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="37ae1-128">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-128">Identity : Global</span></span>

<span data-ttu-id="37ae1-129">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="37ae1-130">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="37ae1-131">DesignateAsPresenter： 公司</span><span class="sxs-lookup"><span data-stu-id="37ae1-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="37ae1-132">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="37ae1-133">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="37ae1-134">同樣地，最後一個項目在清單中， **AdmitAnonymousUsersByDefault**，啟用或停用匿名使用者能夠參與會議。</span><span class="sxs-lookup"><span data-stu-id="37ae1-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="37ae1-135">當檢查會議組態設定，您可能會覺得比較目前的設定，針對預設的等同項目。</span><span class="sxs-lookup"><span data-stu-id="37ae1-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="37ae1-136">您可以檢視預設的會議組態設定執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="37ae1-137">上述命令會建立在記憶體-僅限執行個體全域會議組態設定，每個屬性會使用預設值的執行個體。</span><span class="sxs-lookup"><span data-stu-id="37ae1-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="37ae1-138">不實際會議的組態設定執行命令時建立。</span><span class="sxs-lookup"><span data-stu-id="37ae1-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="37ae1-139">不過，將螢幕上顯示的預設屬性值。</span><span class="sxs-lookup"><span data-stu-id="37ae1-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="37ae1-140">檢查 Edge Server 以及其設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="37ae1-141">可以使用 Windows PowerShell 擷取 edge 伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="37ae1-142">此命令會傳回設定供組織使用的所有 Edge Server 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="37ae1-143">傳回的資訊包括所有的 FQDN 和連接埠設定為每部 Edge Server:</span><span class="sxs-lookup"><span data-stu-id="37ae1-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="37ae1-144">身分識別： EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="37ae1-145">登錄器： Registrar: LYNC SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="37ae1-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="37ae1-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="37ae1-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="37ae1-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="37ae1-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="37ae1-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="37ae1-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="37ae1-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="37ae1-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="37ae1-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="37ae1-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="37ae1-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="37ae1-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="37ae1-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="37ae1-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="37ae1-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="37ae1-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="37ae1-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="37ae1-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="37ae1-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="37ae1-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="37ae1-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="37ae1-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="37ae1-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="37ae1-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="37ae1-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="37ae1-160">AVEdgeExternalFqdn:</span><span class="sxs-lookup"><span data-stu-id="37ae1-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="37ae1-161">InternalInterfaceFqdn:</span><span class="sxs-lookup"><span data-stu-id="37ae1-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="37ae1-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="37ae1-163">DependentServiceList: {Registrar: LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="37ae1-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="37ae1-164">ConferencingServer:LYNC-SE.fabrikam</span><span class="sxs-lookup"><span data-stu-id="37ae1-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="37ae1-165">com、 MediationServer:LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="37ae1-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="37ae1-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="37ae1-166">fabrikam.com}</span></span>

<span data-ttu-id="37ae1-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="37ae1-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="37ae1-168">SiteId: site:fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="37ae1-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="37ae1-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="37ae1-170">版： 5</span><span class="sxs-lookup"><span data-stu-id="37ae1-170">Version : 5</span></span>

<span data-ttu-id="37ae1-171">角色： EdgeServer</span><span class="sxs-lookup"><span data-stu-id="37ae1-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="37ae1-172">檢查同盟設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-172">Check federation settings</span></span>

<span data-ttu-id="37ae1-173">檢查同盟設定，例如是否設定，若答案為"yes，"，FQDN 和連接埠。</span><span class="sxs-lookup"><span data-stu-id="37ae1-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="37ae1-174">啟用並使用 Access Edge 組態設定的全域集合來停用同盟。</span><span class="sxs-lookup"><span data-stu-id="37ae1-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="37ae1-175">除此之外，這些表示同盟已根據全： 同盟啟用整個組織或整個組織的已停用同盟</span><span class="sxs-lookup"><span data-stu-id="37ae1-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="37ae1-176">使用 Windows PowerShell，可以傳回 Access Edge 組態設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="37ae1-177">若要這麼做，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="37ae1-178">接著，該命令會傳回資料類似這樣：</span><span class="sxs-lookup"><span data-stu-id="37ae1-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="37ae1-179">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-179">Identity : Global</span></span>

<span data-ttu-id="37ae1-180">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="37ae1-181">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="37ae1-182">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="37ae1-183">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-183">BeClearingHouse : False</span></span>

<span data-ttu-id="37ae1-184">將 EnablePartnerDiscovery: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="37ae1-185">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="37ae1-186">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="37ae1-187">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="37ae1-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="37ae1-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="37ae1-189">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="37ae1-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="37ae1-190">如果**AllowFederatedUsers**屬性設為 True，這表示，為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="37ae1-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="37ae1-191">（設定為 True 也會表示，在分割網域案例中，您的內部部署使用者將能夠與您在雲端使用者順暢地溝通**AllowFederatedUsers** ）。</span><span class="sxs-lookup"><span data-stu-id="37ae1-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="37ae1-192">若要擷取的 FQDN 和連接埠設定為您的 Edge Server，請參閱 < 在之前的工作 （Edge Server 和其設定）。</span><span class="sxs-lookup"><span data-stu-id="37ae1-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="37ae1-193">啟用全域範圍的聯盟只表示使用者可能可以與同盟使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="37ae1-194">若要判斷任何個別的使用者是否可以與同盟使用者實際通訊需要您檢查指派給該使用者的外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="37ae1-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="37ae1-195">使用 Windows PowerShell，可以傳回外部使用者存取資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="37ae1-196">例如，此命令會傳回通用的外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="37ae1-197">而此命令會傳回所有外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="37ae1-198">傳回的資訊會類似這樣：</span><span class="sxs-lookup"><span data-stu-id="37ae1-198">The returned information will resemble this:</span></span>

<span data-ttu-id="37ae1-199">身分識別： False</span><span class="sxs-lookup"><span data-stu-id="37ae1-199">Identity : False</span></span>

<span data-ttu-id="37ae1-200">描述：</span><span class="sxs-lookup"><span data-stu-id="37ae1-200">Description :</span></span>

<span data-ttu-id="37ae1-201">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="37ae1-202">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="37ae1-203">EnablePublicCloudAccessAudioVideoAccess: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="37ae1-204">EnableOutsideAccess: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="37ae1-205">**EnableFederationAccess**設定為 True，如果指定的原則所管理的使用者能夠與同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="37ae1-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="37ae1-206">檢查封存設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-206">Check archiving settings</span></span>

<span data-ttu-id="37ae1-207">檢查內部和同盟通訊的封存設定值。前驗證設定內部和外部封存，您應該確認已啟用封存。</span><span class="sxs-lookup"><span data-stu-id="37ae1-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="37ae1-208">使用 Windows PowerShell 和 Get-csarchivingconfiguration cmdlet 可驗證封存組態設定：</span><span class="sxs-lookup"><span data-stu-id="37ae1-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="37ae1-209">請注意，封存設定也可以設定在網站範圍。</span><span class="sxs-lookup"><span data-stu-id="37ae1-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="37ae1-210">若要傳回所有封存設定的相關資訊，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="37ae1-211">Get-csarchivingconfiguration cmdlet 會傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="37ae1-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="37ae1-212">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-212">Identity : Global</span></span>

<span data-ttu-id="37ae1-213">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-213">EnableArchiving : False</span></span>

<span data-ttu-id="37ae1-214">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-214">EnablePurging : False</span></span>

<span data-ttu-id="37ae1-215">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="37ae1-216">BlockOnArchiveFailure: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="37ae1-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="37ae1-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="37ae1-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="37ae1-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="37ae1-219">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="37ae1-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="37ae1-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="37ae1-221">如果 EnableArchiving 屬性設為 False，表示沒有通訊工作階段將會封存。</span><span class="sxs-lookup"><span data-stu-id="37ae1-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="37ae1-222">如果您想要封存立即訊息工作階段僅，使用如下所示的命令來啟用 IM 工作階段的封存：</span><span class="sxs-lookup"><span data-stu-id="37ae1-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="37ae1-223">若要封存會議工作階段和立即訊息工作階段，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="37ae1-224">如果您想要比較目前的封存設定具有預設設定，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="37ae1-225">該命令會建立全域封存組態設定中的記憶體-僅限執行個體。</span><span class="sxs-lookup"><span data-stu-id="37ae1-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="37ae1-226">這不是實際的設定集合使用的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="37ae1-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="37ae1-227">不過，它並未顯示所有的封存設定屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="37ae1-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="37ae1-228">您也可以使用此命令來傳回一部封存伺服器的 FQDN:</span><span class="sxs-lookup"><span data-stu-id="37ae1-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="37ae1-229">確認啟用封存之後，然後，您就可以檢視您封存原則，以判斷是否內部及封存外部通訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="37ae1-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="37ae1-230">使用 Get-csarchivingpolicy 指令程式可以擷取封存原則資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="37ae1-231">例如，此命令會傳回通用的封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="37ae1-232">因為封存原則也可以在網站和個別使用者範圍設定，您可能還想要使用此命令，它會傳回所有的封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="37ae1-233">您收到來自 Get-csarchivingpolicy 的資訊會類似這樣：</span><span class="sxs-lookup"><span data-stu-id="37ae1-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="37ae1-234">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-234">Identity : Global</span></span>

<span data-ttu-id="37ae1-235">描述：</span><span class="sxs-lookup"><span data-stu-id="37ae1-235">Description :</span></span>

<span data-ttu-id="37ae1-236">將 ArchiveInternal: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-236">ArchiveInternal : False</span></span>

<span data-ttu-id="37ae1-237">ArchiveExternal: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-237">ArchiveExternal : False</span></span>

<span data-ttu-id="37ae1-238">請注意，根據預設，內部和外部封存中會停用封存原則。</span><span class="sxs-lookup"><span data-stu-id="37ae1-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="37ae1-239">請檢查 CDR 設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-239">Check CDR settings</span></span>

<span data-ttu-id="37ae1-240">檢查端對端、 會議及語音詳細通話記錄的詳細通話記錄 (CDR) 設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="37ae1-241">使用**Get-cscdrconfiguration** cmdlet，可以傳回關於 CDR 設定的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="37ae1-242">例如，此命令會傳回關於 CDR 全域集合的組態設定：</span><span class="sxs-lookup"><span data-stu-id="37ae1-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="37ae1-243">CDR 也可以在網站範圍設定，因為您可能還想要執行此命令，傳回所有 CDR 組態設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="37ae1-244">Get-cscdrconfiguration cmdlet 會傳回每個集合的 CDR 組態設定這類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="37ae1-245">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-245">Identity : Global</span></span>

<span data-ttu-id="37ae1-246">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-246">EnableCDR : True</span></span>

<span data-ttu-id="37ae1-247">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-247">EnablePurging : True</span></span>

<span data-ttu-id="37ae1-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="37ae1-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="37ae1-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="37ae1-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="37ae1-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="37ae1-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="37ae1-251">類似的資訊可以被傳回 qoe 監控使用 Get-csqoeconfiguration 指令程式。</span><span class="sxs-lookup"><span data-stu-id="37ae1-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="37ae1-252">例如，此命令會傳回全域的 QoE 組態設定集合的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="37ae1-253">該資訊將會看起來像：</span><span class="sxs-lookup"><span data-stu-id="37ae1-253">That information will resemble this:</span></span>

<span data-ttu-id="37ae1-254">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-254">Identity : Global</span></span>

<span data-ttu-id="37ae1-255">ExternalConsumerIssuedCertId:</span><span class="sxs-lookup"><span data-stu-id="37ae1-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="37ae1-256">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-256">EnablePurging : True</span></span>

<span data-ttu-id="37ae1-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="37ae1-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="37ae1-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="37ae1-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="37ae1-259">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="37ae1-260">ExternalConsumerName:</span><span class="sxs-lookup"><span data-stu-id="37ae1-260">ExternalConsumerName :</span></span>

<span data-ttu-id="37ae1-261">ExternalConsumerURL:</span><span class="sxs-lookup"><span data-stu-id="37ae1-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="37ae1-262">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-262">EnableQoE : True</span></span>

<span data-ttu-id="37ae1-263">如果您想要比較目前的 CDR 設定與預設 CDR 設定，可以執行這個命令檢閱預設值：</span><span class="sxs-lookup"><span data-stu-id="37ae1-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="37ae1-264">同樣地，可以使用此命令擷取 QoE 監控的預設值：</span><span class="sxs-lookup"><span data-stu-id="37ae1-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="37ae1-265">您也可以藉由執行此命令傳回的監控伺服器的 FQDN:</span><span class="sxs-lookup"><span data-stu-id="37ae1-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="37ae1-266">請檢查語音設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-266">Check voice settings</span></span>

<span data-ttu-id="37ae1-267">系統管理員通常是重要的語音設定都包含在語音原則和語音路由： 語音原則包含判斷對個別使用者 （例如能夠順向或轉接電話），同時公開功能的設定語音路由決定如何 （以及如果） PSTN 之間路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="37ae1-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="37ae1-268">可以使用 Windows PowerShell 擷取語音原則資訊。</span><span class="sxs-lookup"><span data-stu-id="37ae1-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="37ae1-269">例如，此命令會傳回全域語音原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="37ae1-270">而此命令會傳回設定供組織使用的所有語音原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="37ae1-271">Get-csvoicepolicy cmdlet 所傳回的資訊類似如下：</span><span class="sxs-lookup"><span data-stu-id="37ae1-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="37ae1-272">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-272">Identity : Global</span></span>

<span data-ttu-id="37ae1-273">PstnUsages:{}</span><span class="sxs-lookup"><span data-stu-id="37ae1-273">PstnUsages : {}</span></span>

<span data-ttu-id="37ae1-274">描述：</span><span class="sxs-lookup"><span data-stu-id="37ae1-274">Description :</span></span>

<span data-ttu-id="37ae1-275">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-275">AllowSimulRing : True</span></span>

<span data-ttu-id="37ae1-276">AllowCallForwarding: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="37ae1-277">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="37ae1-278">名稱： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="37ae1-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="37ae1-279">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-279">EnableDelegation : True</span></span>

<span data-ttu-id="37ae1-280">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-280">EnableTeamCall : True</span></span>

<span data-ttu-id="37ae1-281">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="37ae1-282">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-282">EnableCallPark : False</span></span>

<span data-ttu-id="37ae1-283">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="37ae1-284">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="37ae1-285">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="37ae1-286">您也可以建立傳回您的語音原則的子集的查詢。</span><span class="sxs-lookup"><span data-stu-id="37ae1-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="37ae1-287">例如，此命令會傳回所有允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="37ae1-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="37ae1-288">而此命令會傳回所有不允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="37ae1-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="37ae1-289">在 Windows PowerShell 中使用 Get-CsVoiceRouting cmdlet 傳回語音路由的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="37ae1-290">該命令會傳回這項目的所有語音路由的資訊：</span><span class="sxs-lookup"><span data-stu-id="37ae1-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="37ae1-291">身分識別： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="37ae1-291">Identity : LocalRoute</span></span>

<span data-ttu-id="37ae1-292">優先順序： 0</span><span class="sxs-lookup"><span data-stu-id="37ae1-292">Priority : 0</span></span>

<span data-ttu-id="37ae1-293">描述：</span><span class="sxs-lookup"><span data-stu-id="37ae1-293">Description :</span></span>

<span data-ttu-id="37ae1-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="37ae1-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="37ae1-295">PstnUsages:{}</span><span class="sxs-lookup"><span data-stu-id="37ae1-295">PstnUsages : {}</span></span>

<span data-ttu-id="37ae1-296">PstnGatewayList:{}</span><span class="sxs-lookup"><span data-stu-id="37ae1-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="37ae1-297">名稱： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="37ae1-297">Name : LocalRoute</span></span>

<span data-ttu-id="37ae1-298">SuppressCallerId:</span><span class="sxs-lookup"><span data-stu-id="37ae1-298">SuppressCallerId :</span></span>

<span data-ttu-id="37ae1-299">AlternateCallerId:</span><span class="sxs-lookup"><span data-stu-id="37ae1-299">AlternateCallerId :</span></span>

<span data-ttu-id="37ae1-300">Lync Server 可讓您建立語音路由，不需要 PSTN 使用方式，而且未指定 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="37ae1-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="37ae1-301">不過，您不能透過語音路由，不需要設定下列兩個屬性值實際上路由通話。</span><span class="sxs-lookup"><span data-stu-id="37ae1-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="37ae1-302">因此，您可能會覺得定期執行此命令，它會傳回任何不需要 PSTN 使用方式的語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="37ae1-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="37ae1-303">同樣地，此命令會傳回任何尚未設定為有 PSTN 閘道的語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="37ae1-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="37ae1-304">請檢查會議服務員設定</span><span class="sxs-lookup"><span data-stu-id="37ae1-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="37ae1-305">檢查 PSTN 電話撥入式會議的會議服務員設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="37ae1-306">僅能使用**Get-csdialinconferencingconfiguration**指令程式擷取會議服務員設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="37ae1-307">這些設定不在 Lync Server Control Panel 中使用。</span><span class="sxs-lookup"><span data-stu-id="37ae1-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="37ae1-308">若要檢視您的會議服務員設定，請使用類似下列項目，它會傳回會議服務員設定全域集合的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="37ae1-309">請注意也可以在網站範圍設定會議服務員設定。</span><span class="sxs-lookup"><span data-stu-id="37ae1-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="37ae1-310">若要傳回所有會議服務員設定的相關資訊，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="37ae1-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="37ae1-311">Get-csdialinconferencingconfiguration cmdlet 會傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="37ae1-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="37ae1-312">身分識別： 全域</span><span class="sxs-lookup"><span data-stu-id="37ae1-312">Identity : Global</span></span>

<span data-ttu-id="37ae1-313">EntryExitAnnouncementsType: UseNames</span><span class="sxs-lookup"><span data-stu-id="37ae1-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="37ae1-314">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="37ae1-314">EnableNameRecording : True</span></span>

<span data-ttu-id="37ae1-315">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="37ae1-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="37ae1-316">如果 EntryExitAnnouncementsEnabledByDefault 設為 False，表示會議宣告已停用。</span><span class="sxs-lookup"><span data-stu-id="37ae1-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="37ae1-317">若要啟用進入與離開宣告，執行 Windows PowerShell 命令類似這樣：</span><span class="sxs-lookup"><span data-stu-id="37ae1-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37ae1-318">另請參閱</span><span class="sxs-lookup"><span data-stu-id="37ae1-318">See Also</span></span>


[<span data-ttu-id="37ae1-319">Get-cssipdomain</span><span class="sxs-lookup"><span data-stu-id="37ae1-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="37ae1-320">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="37ae1-321">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="37ae1-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="37ae1-322">Get-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="37ae1-323">Get-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="37ae1-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="37ae1-324">Get-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="37ae1-325">Get-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="37ae1-326">Get-csqoeconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="37ae1-327">Get-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="37ae1-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="37ae1-328">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="37ae1-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="37ae1-329">Get-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="37ae1-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

