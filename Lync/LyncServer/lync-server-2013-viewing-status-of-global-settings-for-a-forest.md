---
title: Lync Server 2013：查看林中全域設定的狀態
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
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="76750-102">在 Lync Server 2013 中查看林中全域設定的狀態</span><span class="sxs-lookup"><span data-stu-id="76750-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76750-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="76750-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="76750-104">系統管理員應該每月查看 Lync Server 2013 部署的全域設定。</span><span class="sxs-lookup"><span data-stu-id="76750-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="76750-105">這個目標就是針對一組已知的設定來查看已實施的設定，這是一種比較基準設定，可協助保證設定有效，並判斷是否應該更新基準檔。</span><span class="sxs-lookup"><span data-stu-id="76750-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="76750-106">全域設定的變更應該透過變更控制程式來實現，此程式應該包括記錄新設定。</span><span class="sxs-lookup"><span data-stu-id="76750-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="76750-107">在下列各節中將說明應審查的全域設定：</span><span class="sxs-lookup"><span data-stu-id="76750-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="76750-108">檢查一般設定</span><span class="sxs-lookup"><span data-stu-id="76750-108">Check general settings</span></span>

<span data-ttu-id="76750-109">檢查 [一般設定]，包括 Lync Server 2013 支援的會話初始通訊協定（SIP）網域。</span><span class="sxs-lookup"><span data-stu-id="76750-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="76750-110">SIP 網域資訊可以使用 Windows PowerShell 和**CsSipDomain** Cmdlet 傳回。</span><span class="sxs-lookup"><span data-stu-id="76750-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="76750-111">若要返回此資訊，請`Get-CsSipDomain`執行 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="76750-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="76750-112">CsSipDomain 將會針對所有授權 SIP 網域傳回類似以下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="76750-113">身分識別名稱 IsDefault</span><span class="sxs-lookup"><span data-stu-id="76750-113">Identity Name IsDefault</span></span>

<span data-ttu-id="76750-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="76750-114">\-------- ---- ---------</span></span>

<span data-ttu-id="76750-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="76750-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="76750-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="76750-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="76750-117">如果 IsDefault 屬性設定為 True，對應的網域就是您的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="76750-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="76750-118">您可以使用 CsSipDomain Cmdlet 來變更貴組織的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="76750-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="76750-119">不過，您無法只刪除預設的 SIP 網域，因為這樣會讓您不需要預設網域。</span><span class="sxs-lookup"><span data-stu-id="76750-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="76750-120">如果您想要刪除 fabrikam.com 網域（如上一個範例所示），您必須先將 na.fabrikam.com 設定為預設網域。</span><span class="sxs-lookup"><span data-stu-id="76750-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="76750-121">檢查會議設定</span><span class="sxs-lookup"><span data-stu-id="76750-121">Check meeting settings</span></span>

<span data-ttu-id="76750-122">會議設定包括會議原則定義，以及在會議中參與匿名使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="76750-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="76750-123">您可以使用 Windows PowerShell 和**CsMeetingConfiguration** Cmdlet 來檢索會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="76750-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="76750-124">例如，以下命令會傳回有關全域會議設定設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="76750-125">CsMeetingConfiguration –身分識別 "全域" 會議設定設定也可以在網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="76750-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="76750-126">因此，您可能會想要使用下列命令，以傳回所有會議設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="76750-127">**CsMeetingConfiguration** Cmdlet 會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="76750-128">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-128">Identity : Global</span></span>

<span data-ttu-id="76750-129">PstnCallersBypassLobby： True</span><span class="sxs-lookup"><span data-stu-id="76750-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="76750-130">EnableAssignedConferenceType： True</span><span class="sxs-lookup"><span data-stu-id="76750-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="76750-131">DesignateAsPresenter：公司</span><span class="sxs-lookup"><span data-stu-id="76750-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="76750-132">AssignedConferenceTypeByDefault： True</span><span class="sxs-lookup"><span data-stu-id="76750-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="76750-133">AdmitAnonymousUsersByDefault： True</span><span class="sxs-lookup"><span data-stu-id="76750-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="76750-134">同樣地，清單中的最後一個專案**AdmitAnonymousUsersByDefault**，可以啟用或停用匿名使用者參與會議的功能。</span><span class="sxs-lookup"><span data-stu-id="76750-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="76750-135">檢查會議設定時，您可能會發現比較目前的設定與預設對等專案很有用。</span><span class="sxs-lookup"><span data-stu-id="76750-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="76750-136">您可以執行下列命令來查看預設會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="76750-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="76750-137">[上一個] 命令會建立全域會議設定設定的純記憶體實例，該實例會使用每個屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="76750-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="76750-138">當您執行命令時，不會建立實際的會議設定。</span><span class="sxs-lookup"><span data-stu-id="76750-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="76750-139">不過，所有預設屬性值都會顯示在畫面上。</span><span class="sxs-lookup"><span data-stu-id="76750-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="76750-140">檢查邊緣伺服器及其設定</span><span class="sxs-lookup"><span data-stu-id="76750-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="76750-141">您可以使用 Windows PowerShell 來檢索 Edge 伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="76750-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="76750-142">這個命令會傳回您在組織中設定為使用的所有邊緣伺服器的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="76750-143">傳回的資訊包含每個 Edge 伺服器的所有 FQDN 和埠設定：</span><span class="sxs-lookup"><span data-stu-id="76750-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="76750-144">身分識別： EdgeServer： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="76750-145">註冊機構：註冊機構： LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="76750-146">AccessEdgeInternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="76750-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="76750-147">AccessEdgeExternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="76750-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="76750-148">AccessEdgeClientPort：443</span><span class="sxs-lookup"><span data-stu-id="76750-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="76750-149">DataPsomServerPort：8057</span><span class="sxs-lookup"><span data-stu-id="76750-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="76750-150">DataPsomClientPort：444</span><span class="sxs-lookup"><span data-stu-id="76750-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="76750-151">MediaRelayAuthEdgePort：5062</span><span class="sxs-lookup"><span data-stu-id="76750-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="76750-152">MediaRelayAuthInternalTurnTcpPort：443</span><span class="sxs-lookup"><span data-stu-id="76750-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="76750-153">MediaRelayAuthExternalTurnTcpPort：445</span><span class="sxs-lookup"><span data-stu-id="76750-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="76750-154">MediaRelayAuthInternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="76750-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="76750-155">MediaRelayAuthExternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="76750-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="76750-156">MediaCommunicationPortStart：50000</span><span class="sxs-lookup"><span data-stu-id="76750-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="76750-157">MediaComunicationPortCount：10000</span><span class="sxs-lookup"><span data-stu-id="76750-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="76750-158">AccessEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="76750-159">DataEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="76750-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="76750-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="76750-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="76750-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="76750-162">ExternalMrasFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="76750-163">DependentServiceList： {註冊機構： LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="76750-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="76750-164">ConferencingServer： LYNC SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="76750-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="76750-165">com、MediationServer： LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="76750-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="76750-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="76750-166">fabrikam.com}</span></span>

<span data-ttu-id="76750-167">ServiceId： fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="76750-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="76750-168">SiteId： site:fabrikam</span><span class="sxs-lookup"><span data-stu-id="76750-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="76750-169">PoolFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="76750-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="76750-170">版本：5</span><span class="sxs-lookup"><span data-stu-id="76750-170">Version : 5</span></span>

<span data-ttu-id="76750-171">角色： EdgeServer</span><span class="sxs-lookup"><span data-stu-id="76750-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="76750-172">檢查同盟設定</span><span class="sxs-lookup"><span data-stu-id="76750-172">Check federation settings</span></span>

<span data-ttu-id="76750-173">檢查同盟設定（例如是否已設定），如果答案是 "是，"，FQDN 和埠。</span><span class="sxs-lookup"><span data-stu-id="76750-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="76750-174">同盟是透過使用存取邊緣設定的全域集合來啟用和停用。</span><span class="sxs-lookup"><span data-stu-id="76750-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="76750-175">在其他專案中，這些代表將同盟設定為全或全是完全相同：針對整個組織啟用同盟，或針對整個組織停用同盟</span><span class="sxs-lookup"><span data-stu-id="76750-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="76750-176">您可以使用 Windows PowerShell 傳回您的存取邊緣設定。</span><span class="sxs-lookup"><span data-stu-id="76750-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="76750-177">若要執行此動作，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="76750-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="76750-178">接著，該命令會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="76750-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="76750-179">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-179">Identity : Global</span></span>

<span data-ttu-id="76750-180">AllowAnonymousUsers： False</span><span class="sxs-lookup"><span data-stu-id="76750-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="76750-181">AllowFederatedUsers： False</span><span class="sxs-lookup"><span data-stu-id="76750-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="76750-182">AllowOutsideUsers： False</span><span class="sxs-lookup"><span data-stu-id="76750-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="76750-183">BeClearingHouse： False</span><span class="sxs-lookup"><span data-stu-id="76750-183">BeClearingHouse : False</span></span>

<span data-ttu-id="76750-184">EnablePartnerDiscovery： False</span><span class="sxs-lookup"><span data-stu-id="76750-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="76750-185">EnableArchivingDisclaimer： False</span><span class="sxs-lookup"><span data-stu-id="76750-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="76750-186">KeepCrlsUpToDateForPeers： True</span><span class="sxs-lookup"><span data-stu-id="76750-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="76750-187">MarkSourceVerifiableOnOutgoingMessages： True</span><span class="sxs-lookup"><span data-stu-id="76750-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="76750-188">OutgoingTlsCountForFederatedPartners：4</span><span class="sxs-lookup"><span data-stu-id="76750-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="76750-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="76750-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="76750-190">如果**AllowFederatedUsers**屬性設為 True，則表示您的組織已啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="76750-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="76750-191">（將**AllowFederatedUsers**設定為 True 也表示，在分割網域案例中，您的內部部署使用者將能夠與雲端使用者順暢地溝通。）</span><span class="sxs-lookup"><span data-stu-id="76750-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="76750-192">若要取得邊緣伺服器的 FQDN 和埠設定，請參閱上一個工作（邊緣伺服器及其設定）。</span><span class="sxs-lookup"><span data-stu-id="76750-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="76750-193">在全域範圍中啟用同盟，只表示使用者可能會與聯盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="76750-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="76750-194">若要判斷是否有任何個別的使用者都能實際與同盟使用者通訊，需要您檢查指派給該使用者的外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="76750-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="76750-195">外部使用者存取訊號可以使用 Windows PowerShell 傳回。</span><span class="sxs-lookup"><span data-stu-id="76750-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="76750-196">例如，這個命令會傳回全域外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="76750-197">這個命令會傳回所有外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="76750-198">傳回的資訊將如下所示：</span><span class="sxs-lookup"><span data-stu-id="76750-198">The returned information will resemble this:</span></span>

<span data-ttu-id="76750-199">身分識別： False</span><span class="sxs-lookup"><span data-stu-id="76750-199">Identity : False</span></span>

<span data-ttu-id="76750-200">說明</span><span class="sxs-lookup"><span data-stu-id="76750-200">Description :</span></span>

<span data-ttu-id="76750-201">EnableFederationAccess： False</span><span class="sxs-lookup"><span data-stu-id="76750-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="76750-202">EnablePublicCloudAccess： False</span><span class="sxs-lookup"><span data-stu-id="76750-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="76750-203">EnablePublicCloudAccessAudioVideoAccess： False</span><span class="sxs-lookup"><span data-stu-id="76750-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="76750-204">EnableOutsideAccess： False</span><span class="sxs-lookup"><span data-stu-id="76750-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="76750-205">如果**EnableFederationAccess**設定為 True，則由指定原則管理的使用者可以與聯盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="76750-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="76750-206">檢查存檔設定</span><span class="sxs-lookup"><span data-stu-id="76750-206">Check archiving settings</span></span>

<span data-ttu-id="76750-207">檢查內部和聯盟通訊的封存設定。在驗證內部和外部封存的設定前，您應該確認已啟用封存。</span><span class="sxs-lookup"><span data-stu-id="76750-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="76750-208">您可以使用 Windows PowerShell 和 CsArchivingConfiguration Cmdlet 來驗證封存配置設定：</span><span class="sxs-lookup"><span data-stu-id="76750-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="76750-209">請注意，您也可以在網站範圍中設定存檔設定。</span><span class="sxs-lookup"><span data-stu-id="76750-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="76750-210">若要傳回所有存檔設定的相關資訊，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="76750-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="76750-211">CsArchivingConfiguration Cmdlet 會傳回類似以下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="76750-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="76750-212">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-212">Identity : Global</span></span>

<span data-ttu-id="76750-213">EnableArchiving： False</span><span class="sxs-lookup"><span data-stu-id="76750-213">EnableArchiving : False</span></span>

<span data-ttu-id="76750-214">EnablePurging： False</span><span class="sxs-lookup"><span data-stu-id="76750-214">EnablePurging : False</span></span>

<span data-ttu-id="76750-215">PurgeExportedArchivesOnly： False</span><span class="sxs-lookup"><span data-stu-id="76750-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="76750-216">BlockOnArchiveFailure： False</span><span class="sxs-lookup"><span data-stu-id="76750-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="76750-217">KeepArchivingDataForDays：14</span><span class="sxs-lookup"><span data-stu-id="76750-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="76750-218">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="76750-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="76750-219">ArchiveDuplicateMessages： True</span><span class="sxs-lookup"><span data-stu-id="76750-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="76750-220">CachePurgingInterval：24</span><span class="sxs-lookup"><span data-stu-id="76750-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="76750-221">如果 EnableArchiving 屬性設為 False，即表示不會封存任何通訊會話。</span><span class="sxs-lookup"><span data-stu-id="76750-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="76750-222">如果您只想封存立即訊息會話，請使用如下所示的命令來啟用 IM 會話的存檔：</span><span class="sxs-lookup"><span data-stu-id="76750-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="76750-223">若要封存會議會話與立即訊息會話，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="76750-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="76750-224">如果您想要將目前的存檔設定與預設設定進行比較，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="76750-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="76750-225">該命令會建立全域存檔設定的內部記憶體式實例。</span><span class="sxs-lookup"><span data-stu-id="76750-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="76750-226">這不是 Lync Server 所使用的真正設定集合。</span><span class="sxs-lookup"><span data-stu-id="76750-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="76750-227">不過，它會顯示所有存檔設定屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="76750-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="76750-228">您也可以使用這個命令來傳回封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="76750-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="76750-229">確認已啟用封存之後，您就可以查看您的封存原則，判斷內部和外部通訊會話是否已歸檔。</span><span class="sxs-lookup"><span data-stu-id="76750-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="76750-230">您可以使用 CsArchivingPolicy Cmdlet 來檢索存檔原則資訊。</span><span class="sxs-lookup"><span data-stu-id="76750-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="76750-231">例如，這個命令會傳回全域存檔原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="76750-232">因為歸檔原則也可以在網站和每個使用者的範圍內設定，所以您可能也會想要使用此命令，以傳回所有歸檔原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="76750-233">從 CsArchivingPolicy 收到的資訊將如下所示：</span><span class="sxs-lookup"><span data-stu-id="76750-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="76750-234">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-234">Identity : Global</span></span>

<span data-ttu-id="76750-235">說明</span><span class="sxs-lookup"><span data-stu-id="76750-235">Description :</span></span>

<span data-ttu-id="76750-236">ArchiveInternal： False</span><span class="sxs-lookup"><span data-stu-id="76750-236">ArchiveInternal : False</span></span>

<span data-ttu-id="76750-237">ArchiveExternal： False</span><span class="sxs-lookup"><span data-stu-id="76750-237">ArchiveExternal : False</span></span>

<span data-ttu-id="76750-238">請注意，在預設情況下，內部和外部封存都會在歸檔原則中停用。</span><span class="sxs-lookup"><span data-stu-id="76750-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="76750-239">檢查 CDR 設定</span><span class="sxs-lookup"><span data-stu-id="76750-239">Check CDR settings</span></span>

<span data-ttu-id="76750-240">檢查對等、會議和語音通話詳細資料錄製的通話詳細資料記錄（CDR）設定。</span><span class="sxs-lookup"><span data-stu-id="76750-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="76750-241">您的 CDR 設定的詳細資訊可以使用**CsCdrConfiguration** Cmdlet 傳回。</span><span class="sxs-lookup"><span data-stu-id="76750-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="76750-242">例如，這個命令會傳回有關 CDR 配置設定的全域集合的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="76750-243">因為 CDR 也可以在網站範圍進行設定，所以您可能也想要執行此命令，以傳回所有 CDR 設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="76750-244">CsCdrConfiguration Cmdlet 會針對每個 CDR 設定設定的集合傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="76750-245">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-245">Identity : Global</span></span>

<span data-ttu-id="76750-246">EnableCDR： True</span><span class="sxs-lookup"><span data-stu-id="76750-246">EnableCDR : True</span></span>

<span data-ttu-id="76750-247">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="76750-247">EnablePurging : True</span></span>

<span data-ttu-id="76750-248">KeepCallDetailForDays：60</span><span class="sxs-lookup"><span data-stu-id="76750-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="76750-249">KeepErrorReportForDays：60</span><span class="sxs-lookup"><span data-stu-id="76750-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="76750-250">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="76750-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="76750-251">您可以使用 CsQoEConfiguration Cmdlet 傳回 QoE 監視的類似資訊。</span><span class="sxs-lookup"><span data-stu-id="76750-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="76750-252">例如，這個命令會傳回 QoE 設定的全域集合資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="76750-253">該資訊將如下所示：</span><span class="sxs-lookup"><span data-stu-id="76750-253">That information will resemble this:</span></span>

<span data-ttu-id="76750-254">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-254">Identity : Global</span></span>

<span data-ttu-id="76750-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="76750-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="76750-256">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="76750-256">EnablePurging : True</span></span>

<span data-ttu-id="76750-257">KeepQoEDataForDays：60</span><span class="sxs-lookup"><span data-stu-id="76750-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="76750-258">PurgeHourOfDay：1</span><span class="sxs-lookup"><span data-stu-id="76750-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="76750-259">EnableExternalConsumer： False</span><span class="sxs-lookup"><span data-stu-id="76750-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="76750-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="76750-260">ExternalConsumerName :</span></span>

<span data-ttu-id="76750-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="76750-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="76750-262">EnableQoE： True</span><span class="sxs-lookup"><span data-stu-id="76750-262">EnableQoE : True</span></span>

<span data-ttu-id="76750-263">如果您想要將目前的 CDR 設定與預設的 CDR 設定進行比較，您可以執行以下命令來查看預設值：</span><span class="sxs-lookup"><span data-stu-id="76750-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="76750-264">同樣地，您可以使用此命令來檢索 QoE 監視的預設值：</span><span class="sxs-lookup"><span data-stu-id="76750-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="76750-265">您也可以執行此命令，以傳回監視伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="76750-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="76750-266">檢查語音設定</span><span class="sxs-lookup"><span data-stu-id="76750-266">Check voice settings</span></span>

<span data-ttu-id="76750-267">在語音原則和語音路由中，語音原則通常都包含管理員的重要資訊：語音原則包含決定個別使用者所公開之功能的設定（例如轉寄或轉接來電的能力），同時語音路由決定如何在 PSTN 上路由（以及 if）通話。</span><span class="sxs-lookup"><span data-stu-id="76750-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="76750-268">您可以使用 Windows PowerShell 來檢索語音原則資訊。</span><span class="sxs-lookup"><span data-stu-id="76750-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="76750-269">例如，這個命令會傳回有關全域語音原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="76750-270">這個命令會傳回已設定為在組織中使用之所有語音原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="76750-271">CsVoicePolicy Cmdlet 傳回的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="76750-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="76750-272">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-272">Identity : Global</span></span>

<span data-ttu-id="76750-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="76750-273">PstnUsages : {}</span></span>

<span data-ttu-id="76750-274">說明</span><span class="sxs-lookup"><span data-stu-id="76750-274">Description :</span></span>

<span data-ttu-id="76750-275">AllowSimulRing： True</span><span class="sxs-lookup"><span data-stu-id="76750-275">AllowSimulRing : True</span></span>

<span data-ttu-id="76750-276">AllowCallForwarding： True</span><span class="sxs-lookup"><span data-stu-id="76750-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="76750-277">AllowPSTNReRouting： True</span><span class="sxs-lookup"><span data-stu-id="76750-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="76750-278">名稱： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="76750-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="76750-279">EnableDelegation： True</span><span class="sxs-lookup"><span data-stu-id="76750-279">EnableDelegation : True</span></span>

<span data-ttu-id="76750-280">EnableTeamCall： True</span><span class="sxs-lookup"><span data-stu-id="76750-280">EnableTeamCall : True</span></span>

<span data-ttu-id="76750-281">EnableCallTransfer： True</span><span class="sxs-lookup"><span data-stu-id="76750-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="76750-282">EnableCallPark： False</span><span class="sxs-lookup"><span data-stu-id="76750-282">EnableCallPark : False</span></span>

<span data-ttu-id="76750-283">EnableMaliciousCallTracing： False</span><span class="sxs-lookup"><span data-stu-id="76750-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="76750-284">EnableBWPolicyOverride： False</span><span class="sxs-lookup"><span data-stu-id="76750-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="76750-285">PreventPSTNTollBypass： False</span><span class="sxs-lookup"><span data-stu-id="76750-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="76750-286">您也可以建立傳回您語音原則子集的查詢。</span><span class="sxs-lookup"><span data-stu-id="76750-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="76750-287">例如，這個命令會傳回所有允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="76750-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="76750-288">這個命令會傳回所有不允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="76750-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="76750-289">在 Windows PowerShell 中，請使用 CsVoiceRouting Cmdlet 傳回有關語音路由的資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="76750-290">該命令會傳回所有語音路由等相關資訊：</span><span class="sxs-lookup"><span data-stu-id="76750-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="76750-291">身分識別： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="76750-291">Identity : LocalRoute</span></span>

<span data-ttu-id="76750-292">優先順序：0</span><span class="sxs-lookup"><span data-stu-id="76750-292">Priority : 0</span></span>

<span data-ttu-id="76750-293">說明</span><span class="sxs-lookup"><span data-stu-id="76750-293">Description :</span></span>

<span data-ttu-id="76750-294">NumberPattern： ^ （\\+ 1\[0-9\]{10}） $</span><span class="sxs-lookup"><span data-stu-id="76750-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="76750-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="76750-295">PstnUsages : {}</span></span>

<span data-ttu-id="76750-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="76750-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="76750-297">名稱： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="76750-297">Name : LocalRoute</span></span>

<span data-ttu-id="76750-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="76750-298">SuppressCallerId :</span></span>

<span data-ttu-id="76750-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="76750-299">AlternateCallerId :</span></span>

<span data-ttu-id="76750-300">Lync Server 可讓您建立沒有 PSTN 使用狀況且沒有指定 PSTN 閘道的語音路由。</span><span class="sxs-lookup"><span data-stu-id="76750-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="76750-301">不過，您無法實際路由呼叫的語音路線沒有設定這兩個屬性值。</span><span class="sxs-lookup"><span data-stu-id="76750-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="76750-302">因此，您可能會發現定期執行此命令會很有用，這會傳回沒有 PSTN 用法之任何語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="76750-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="76750-303">同樣地，這個命令會傳回尚未設定為有 PSTN 閘道之任何語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="76750-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="76750-304">檢查會議助理設定</span><span class="sxs-lookup"><span data-stu-id="76750-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="76750-305">查看 PSTN 電話撥入式會議的會議助理設定。</span><span class="sxs-lookup"><span data-stu-id="76750-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="76750-306">只能使用**CsDialInConferencingConfiguration** Cmdlet 來檢索會議助理設定。</span><span class="sxs-lookup"><span data-stu-id="76750-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="76750-307">[Lync Server 控制台] 無法使用這些設定。</span><span class="sxs-lookup"><span data-stu-id="76750-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="76750-308">若要查看您的會議助理設定，請使用類似下列的 Windows PowerShell 命令，這會傳回會議助理設定的全域集合：</span><span class="sxs-lookup"><span data-stu-id="76750-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="76750-309">請注意，會議助理設定也可以在網站範圍中設定。</span><span class="sxs-lookup"><span data-stu-id="76750-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="76750-310">若要傳回所有會議助理設定的相關資訊，請改為使用此命令：</span><span class="sxs-lookup"><span data-stu-id="76750-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="76750-311">CsDialInConferencingConfiguration Cmdlet 會傳回類似以下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="76750-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="76750-312">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="76750-312">Identity : Global</span></span>

<span data-ttu-id="76750-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="76750-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="76750-314">EnableNameRecording： True</span><span class="sxs-lookup"><span data-stu-id="76750-314">EnableNameRecording : True</span></span>

<span data-ttu-id="76750-315">EntryExitAnnouncementsEnabledByDefault： False</span><span class="sxs-lookup"><span data-stu-id="76750-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="76750-316">如果 EntryExitAnnouncementsEnabledByDefault 設定為 False，即表示會議宣告已停用。</span><span class="sxs-lookup"><span data-stu-id="76750-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="76750-317">若要啟用進入及結束宣告，請執行如下所示的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="76750-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76750-318">請參閱</span><span class="sxs-lookup"><span data-stu-id="76750-318">See Also</span></span>


[<span data-ttu-id="76750-319">CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="76750-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="76750-320">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="76750-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="76750-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="76750-322">CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="76750-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="76750-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="76750-324">CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="76750-325">CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="76750-326">CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="76750-327">CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="76750-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="76750-328">CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="76750-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="76750-329">CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="76750-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

