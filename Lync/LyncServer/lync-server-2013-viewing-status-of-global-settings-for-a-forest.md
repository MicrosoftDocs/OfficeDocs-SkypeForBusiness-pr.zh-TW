---
title: Lync Server 2013：查看樹系的全域設定狀態
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
ms.openlocfilehash: 7922fe79d97a1fa83fdaa5afbc1eeddee8523e37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535580"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="3fb53-102">在 Lync Server 2013 中查看樹系全域設定的狀態</span><span class="sxs-lookup"><span data-stu-id="3fb53-102">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fb53-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="3fb53-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="3fb53-104">管理員應該每月檢查 Lync Server 2013 部署的全域設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="3fb53-105">目標是複查針對一組已知設定所實施的設定，這是一個基準設定，可協助保證設定有效，並判斷是否應該更新基準檔。</span><span class="sxs-lookup"><span data-stu-id="3fb53-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="3fb53-106">對全域設定所做的變更應透過應包含記錄新設定的變更控制過程來實施。</span><span class="sxs-lookup"><span data-stu-id="3fb53-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="3fb53-107">下列各節將說明應該檢查的全域設定：</span><span class="sxs-lookup"><span data-stu-id="3fb53-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="3fb53-108">檢查一般設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-108">Check general settings</span></span>

<span data-ttu-id="3fb53-109">檢查 [一般設定]，包括 Lync Server 2013 (SIP) 網域的支援的會話初始通訊協定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="3fb53-110">SIP 網域資訊可使用 Windows PowerShell 和 **Get-CsSipDomain** Cmdlet 傳回。</span><span class="sxs-lookup"><span data-stu-id="3fb53-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="3fb53-111">若要傳回此資訊，請執行 `Get-CsSipDomain` Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3fb53-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="3fb53-112">Get-CsSipDomain 會針對所有已獲授權的 SIP 網域，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="3fb53-113">身分識別名稱 IsDefault</span><span class="sxs-lookup"><span data-stu-id="3fb53-113">Identity Name IsDefault</span></span>

<span data-ttu-id="3fb53-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="3fb53-114">\-------- ---- ---------</span></span>

<span data-ttu-id="3fb53-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="3fb53-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="3fb53-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="3fb53-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="3fb53-117">如果 IsDefault 屬性設定為 True，對應的網域就是您的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="3fb53-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="3fb53-118">您可以使用 Set-CsSipDomain Cmdlet 變更組織的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="3fb53-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="3fb53-119">不過，您不能只刪除預設的 SIP 網域，因為這會讓您沒有預設網域。</span><span class="sxs-lookup"><span data-stu-id="3fb53-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="3fb53-120">如果您想要刪除 fabrikam.com 網域 (如先前範例) 所示，您必須先將 na.fabrikam.com 設定為您的預設網域。</span><span class="sxs-lookup"><span data-stu-id="3fb53-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="3fb53-121">檢查會議設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-121">Check meeting settings</span></span>

<span data-ttu-id="3fb53-122">會議設定包括會議原則定義，以及在會議中參與匿名使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="3fb53-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="3fb53-123">您可以使用 Windows PowerShell 和 **Get-CsMeetingConfiguration** Cmdlet 來找回會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="3fb53-124">例如，下列命令會傳回全域會議設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="3fb53-125">Get-CsMeetingConfiguration –身分識別 "Global" 會議設定設定也可以在網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="3fb53-126">因此，您可能會想要使用下列命令，該命令會傳回所有會議設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="3fb53-127">**Get-CsMeetingConfiguration** Cmdlet 會傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="3fb53-128">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-128">Identity : Global</span></span>

<span data-ttu-id="3fb53-129">PstnCallersBypassLobby： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="3fb53-130">EnableAssignedConferenceType： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="3fb53-131">DesignateAsPresenter：公司</span><span class="sxs-lookup"><span data-stu-id="3fb53-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="3fb53-132">AssignedConferenceTypeByDefault： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="3fb53-133">AdmitAnonymousUsersByDefault： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="3fb53-134">同樣地，清單中的最後一個專案會 **AdmitAnonymousUsersByDefault**，啟用或停用匿名使用者參與會議的功能。</span><span class="sxs-lookup"><span data-stu-id="3fb53-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="3fb53-135">檢查會議設定時，您可能會發現比較目前設定與預設對等專案是很有用的。</span><span class="sxs-lookup"><span data-stu-id="3fb53-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="3fb53-136">您可以執行下列命令來查看預設會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="3fb53-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3fb53-137">上一個命令會建立全域會議設定（僅限記憶體）實例的全域會議設定，此範例會使用每個屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="3fb53-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="3fb53-138">當您執行此命令時，並不會建立實際的會議設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="3fb53-139">不過，所有的預設屬性值都會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="3fb53-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="3fb53-140">檢查 Edge Server 及其設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="3fb53-141">您可以使用 Windows PowerShell 來找回 Edge Server 資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="3fb53-142">此命令會傳回設定供組織使用之所有 Edge Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="3fb53-143">傳回的資訊包含各 Edge Server 的所有 FQDN 和埠設定：</span><span class="sxs-lookup"><span data-stu-id="3fb53-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="3fb53-144">Identity： Edgeserver atl-edge： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="3fb53-145">註冊機構：報名者： LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3fb53-146">AccessEdgeInternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="3fb53-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="3fb53-147">AccessEdgeExternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="3fb53-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="3fb53-148">AccessEdgeClientPort：443</span><span class="sxs-lookup"><span data-stu-id="3fb53-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="3fb53-149">DataPsomServerPort：8057</span><span class="sxs-lookup"><span data-stu-id="3fb53-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="3fb53-150">DataPsomClientPort：444</span><span class="sxs-lookup"><span data-stu-id="3fb53-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="3fb53-151">MediaRelayAuthEdgePort：5062</span><span class="sxs-lookup"><span data-stu-id="3fb53-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="3fb53-152">MediaRelayAuthInternalTurnTcpPort：443</span><span class="sxs-lookup"><span data-stu-id="3fb53-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="3fb53-153">MediaRelayAuthExternalTurnTcpPort：445</span><span class="sxs-lookup"><span data-stu-id="3fb53-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="3fb53-154">MediaRelayAuthInternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="3fb53-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="3fb53-155">MediaRelayAuthExternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="3fb53-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="3fb53-156">MediaCommunicationPortStart：50000</span><span class="sxs-lookup"><span data-stu-id="3fb53-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="3fb53-157">MediaComunicationPortCount：10000</span><span class="sxs-lookup"><span data-stu-id="3fb53-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="3fb53-158">AccessEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3fb53-159">DataEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3fb53-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="3fb53-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="3fb53-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="3fb53-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="3fb53-162">ExternalMrasFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3fb53-163">DependentServiceList： {註冊機構： LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="3fb53-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="3fb53-164">ConferencingServer： LYNC-SE。 fabrikam</span><span class="sxs-lookup"><span data-stu-id="3fb53-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="3fb53-165">com，MediationServer： LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="3fb53-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="3fb53-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="3fb53-166">fabrikam.com}</span></span>

<span data-ttu-id="3fb53-167">ServiceId： fabrikam.com-Edgeserver atl-edge-2</span><span class="sxs-lookup"><span data-stu-id="3fb53-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="3fb53-168">SiteId：網站:fabrikam</span><span class="sxs-lookup"><span data-stu-id="3fb53-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="3fb53-169">PoolFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb53-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="3fb53-170">版本：5</span><span class="sxs-lookup"><span data-stu-id="3fb53-170">Version : 5</span></span>

<span data-ttu-id="3fb53-171">角色： Edgeserver atl-edge</span><span class="sxs-lookup"><span data-stu-id="3fb53-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="3fb53-172">檢查同盟設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-172">Check federation settings</span></span>

<span data-ttu-id="3fb53-173">檢查同盟設定，例如是否已設定，以及是否為「是」，FQDN 和埠。</span><span class="sxs-lookup"><span data-stu-id="3fb53-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="3fb53-174">使用 Access Edge 設定的全域集合，啟用並停用同盟。</span><span class="sxs-lookup"><span data-stu-id="3fb53-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="3fb53-175">此外，這些也意味著同盟設定為全部或無基準：已為整個組織啟用同盟，或對整個組織停用同盟</span><span class="sxs-lookup"><span data-stu-id="3fb53-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="3fb53-176">您可以使用 Windows PowerShell 傳回您的 Access Edge 設定設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="3fb53-177">若要這麼做，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="3fb53-178">接著，該命令會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="3fb53-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="3fb53-179">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-179">Identity : Global</span></span>

<span data-ttu-id="3fb53-180">AllowAnonymousUsers： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="3fb53-181">AllowFederatedUsers： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="3fb53-182">AllowOutsideUsers： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="3fb53-183">BeClearingHouse： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-183">BeClearingHouse : False</span></span>

<span data-ttu-id="3fb53-184">EnablePartnerDiscovery： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="3fb53-185">EnableArchivingDisclaimer： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="3fb53-186">KeepCrlsUpToDateForPeers： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="3fb53-187">MarkSourceVerifiableOnOutgoingMessages： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="3fb53-188">OutgoingTlsCountForFederatedPartners：4</span><span class="sxs-lookup"><span data-stu-id="3fb53-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="3fb53-189">RoutingMethod： UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="3fb53-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="3fb53-190">如果 **AllowFederatedUsers** 屬性設定為 True，表示您的組織已啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="3fb53-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="3fb53-191"> (設定 **AllowFederatedUsers** 設定為 True 也表示，在分割網域案例中，您的內部部署使用者將能夠與您的雲端使用者無縫通訊。 ) </span><span class="sxs-lookup"><span data-stu-id="3fb53-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="3fb53-192">若要取得 Edge Server 的 FQDN 及埠設定，請參閱上一個工作 (Edge Server 及其設定) 。</span><span class="sxs-lookup"><span data-stu-id="3fb53-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="3fb53-193">在全域範圍啟用同盟，只表示使用者可能會與同盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="3fb53-194">若要判斷是否有任何個別使用者可以實際與同盟使用者通訊，需要檢查指派給該使用者的外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="3fb53-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="3fb53-195">您可以使用 Windows PowerShell 傳回外部使用者存取訊號。</span><span class="sxs-lookup"><span data-stu-id="3fb53-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="3fb53-196">例如，下列命令會傳回全域外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="3fb53-197">而且，此命令會傳回所有外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="3fb53-198">傳回的資訊將如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fb53-198">The returned information will resemble this:</span></span>

<span data-ttu-id="3fb53-199">身分識別： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-199">Identity : False</span></span>

<span data-ttu-id="3fb53-200">描述：</span><span class="sxs-lookup"><span data-stu-id="3fb53-200">Description :</span></span>

<span data-ttu-id="3fb53-201">EnableFederationAccess： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="3fb53-202">EnablePublicCloudAccess： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="3fb53-203">EnablePublicCloudAccessAudioVideoAccess： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="3fb53-204">EnableOutsideAccess： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="3fb53-205">如果 **EnableFederationAccess** 設定為 True，則指定原則所管理的使用者可以與同盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="3fb53-206">檢查封存設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-206">Check archiving settings</span></span>

<span data-ttu-id="3fb53-207">檢查內部及同盟通訊的封存設定。在驗證內部和外部封存的設定之前，您應該確認已啟用封存。</span><span class="sxs-lookup"><span data-stu-id="3fb53-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="3fb53-208">您可以使用 Windows PowerShell 和 Get-CsArchivingConfiguration Cmdlet 來驗證封存設定設定：</span><span class="sxs-lookup"><span data-stu-id="3fb53-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="3fb53-209">請注意，也可以在網站範圍中設定封存設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="3fb53-210">若要傳回所有封存設定的資訊，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="3fb53-211">Get-CsArchivingConfiguration Cmdlet 會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="3fb53-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="3fb53-212">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-212">Identity : Global</span></span>

<span data-ttu-id="3fb53-213">EnableArchiving： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-213">EnableArchiving : False</span></span>

<span data-ttu-id="3fb53-214">EnablePurging： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-214">EnablePurging : False</span></span>

<span data-ttu-id="3fb53-215">PurgeExportedArchivesOnly： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="3fb53-216">BlockOnArchiveFailure： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="3fb53-217">KeepArchivingDataForDays：14</span><span class="sxs-lookup"><span data-stu-id="3fb53-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="3fb53-218">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="3fb53-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="3fb53-219">ArchiveDuplicateMessages： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="3fb53-220">CachePurgingInterval：24</span><span class="sxs-lookup"><span data-stu-id="3fb53-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="3fb53-221">如果 EnableArchiving 屬性設定為 False，表示將不會封存任何通訊會話。</span><span class="sxs-lookup"><span data-stu-id="3fb53-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="3fb53-222">如果您只想要封存立即訊息會話，請使用類似下列的命令來啟用 IM 會話的封存：</span><span class="sxs-lookup"><span data-stu-id="3fb53-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="3fb53-223">若要封存會議會話和立即訊息會話，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="3fb53-224">如果您想要將目前的封存設定與預設設定進行比較，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3fb53-225">該命令會為全域封存設定設定建立僅限記憶體的實例。</span><span class="sxs-lookup"><span data-stu-id="3fb53-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="3fb53-226">這不是 Lync Server 所使用之實際設定的集合。</span><span class="sxs-lookup"><span data-stu-id="3fb53-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="3fb53-227">不過，它會顯示所有封存配置屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="3fb53-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="3fb53-228">您也可以使用此命令傳回封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="3fb53-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="3fb53-229">在您確認封存已啟用之後，您就可以查看封存原則，判斷是否要封存內部和外部通訊會話。</span><span class="sxs-lookup"><span data-stu-id="3fb53-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="3fb53-230">您可以使用 Get-CsArchivingPolicy Cmdlet 來檢索封存原則資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="3fb53-231">例如，下列命令會傳回全域封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="3fb53-232">因為封存原則也可以在網站和個別使用者範圍內設定，所以您也可以使用此命令，傳回所有封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="3fb53-233">您從 Get-CsArchivingPolicy 取得的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fb53-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="3fb53-234">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-234">Identity : Global</span></span>

<span data-ttu-id="3fb53-235">描述：</span><span class="sxs-lookup"><span data-stu-id="3fb53-235">Description :</span></span>

<span data-ttu-id="3fb53-236">ArchiveInternal： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-236">ArchiveInternal : False</span></span>

<span data-ttu-id="3fb53-237">ArchiveExternal： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-237">ArchiveExternal : False</span></span>

<span data-ttu-id="3fb53-238">請注意，預設會停用封存原則中的內部和外部封存。</span><span class="sxs-lookup"><span data-stu-id="3fb53-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="3fb53-239">檢查 CDR 設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-239">Check CDR settings</span></span>

<span data-ttu-id="3fb53-240">檢查 (CDR) 設定對等、會議及語音通話詳細資料記錄的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="3fb53-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="3fb53-241">您可以使用 **Get-CsCdrConfiguration** CMDLET 傳回 CDR 設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="3fb53-242">例如，下列命令會傳回全域 CDR 設定設定集合的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="3fb53-243">因為 CDR 也可以在網站範圍上進行設定，所以您也可能會想要執行此命令，以傳回所有 CDR 設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="3fb53-244">Get-CsCdrConfiguration Cmdlet 會針對每個 CDR 設定設定的集合，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="3fb53-245">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-245">Identity : Global</span></span>

<span data-ttu-id="3fb53-246">EnableCDR： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-246">EnableCDR : True</span></span>

<span data-ttu-id="3fb53-247">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-247">EnablePurging : True</span></span>

<span data-ttu-id="3fb53-248">KeepCallDetailForDays：60</span><span class="sxs-lookup"><span data-stu-id="3fb53-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="3fb53-249">KeepErrorReportForDays：60</span><span class="sxs-lookup"><span data-stu-id="3fb53-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="3fb53-250">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="3fb53-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="3fb53-251">您可以透過使用 Get-CsQoEConfiguration Cmdlet，傳回 QoE 監視的類似資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="3fb53-252">例如，下列命令會傳回全域 QoE 配置設定集合的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="3fb53-253">此資訊會類似如下：</span><span class="sxs-lookup"><span data-stu-id="3fb53-253">That information will resemble this:</span></span>

<span data-ttu-id="3fb53-254">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-254">Identity : Global</span></span>

<span data-ttu-id="3fb53-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="3fb53-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="3fb53-256">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-256">EnablePurging : True</span></span>

<span data-ttu-id="3fb53-257">KeepQoEDataForDays：60</span><span class="sxs-lookup"><span data-stu-id="3fb53-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="3fb53-258">PurgeHourOfDay：1</span><span class="sxs-lookup"><span data-stu-id="3fb53-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="3fb53-259">EnableExternalConsumer： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="3fb53-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="3fb53-260">ExternalConsumerName :</span></span>

<span data-ttu-id="3fb53-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="3fb53-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="3fb53-262">EnableQoE： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-262">EnableQoE : True</span></span>

<span data-ttu-id="3fb53-263">如果您想要將目前的 CDR 設定與預設 CDR 設定進行比較，可以執行下列命令來複查預設值：</span><span class="sxs-lookup"><span data-stu-id="3fb53-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3fb53-264">同樣地，您可以使用下列命令來檢索 QoE 監視的預設值：</span><span class="sxs-lookup"><span data-stu-id="3fb53-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="3fb53-265">您也可以執行下列命令，傳回監控伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="3fb53-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="3fb53-266">檢查語音設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-266">Check voice settings</span></span>

<span data-ttu-id="3fb53-267">語音設定通常對系統管理員來說包含在語音原則和語音路由中：語音原則包含決定個別使用者的功能 (例如轉寄或轉接) 呼叫的功能）的設定，而語音路由會決定) 呼叫在 PSTN 間路由 (和呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="3fb53-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="3fb53-268">語音原則資訊可透過使用 Windows PowerShell 進行檢索。</span><span class="sxs-lookup"><span data-stu-id="3fb53-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="3fb53-269">例如，下列命令會傳回有關通用語音原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="3fb53-270">而且此命令會傳回設定供組織使用之所有語音原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="3fb53-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="3fb53-271">Get-CsVoicePolicy Cmdlet 所傳回的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fb53-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="3fb53-272">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-272">Identity : Global</span></span>

<span data-ttu-id="3fb53-273">PstnUsages： {}</span><span class="sxs-lookup"><span data-stu-id="3fb53-273">PstnUsages : {}</span></span>

<span data-ttu-id="3fb53-274">描述：</span><span class="sxs-lookup"><span data-stu-id="3fb53-274">Description :</span></span>

<span data-ttu-id="3fb53-275">AllowSimulRing： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-275">AllowSimulRing : True</span></span>

<span data-ttu-id="3fb53-276">AllowCallForwarding： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="3fb53-277">AllowPSTNReRouting： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="3fb53-278">名稱： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="3fb53-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="3fb53-279">EnableDelegation： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-279">EnableDelegation : True</span></span>

<span data-ttu-id="3fb53-280">EnableTeamCall： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-280">EnableTeamCall : True</span></span>

<span data-ttu-id="3fb53-281">EnableCallTransfer： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="3fb53-282">EnableCallPark： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-282">EnableCallPark : False</span></span>

<span data-ttu-id="3fb53-283">EnableMaliciousCallTracing： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="3fb53-284">EnableBWPolicyOverride： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="3fb53-285">PreventPSTNTollBypass： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="3fb53-286">您也可以建立傳回語音原則子集的查詢。</span><span class="sxs-lookup"><span data-stu-id="3fb53-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="3fb53-287">例如，此命令會傳回所有允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="3fb53-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="3fb53-288">而且，此命令會傳回所有不允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="3fb53-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="3fb53-289">在 [Windows PowerShell] 中，使用 Get-CsVoiceRouting Cmdlet 傳回語音路由的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3fb53-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="3fb53-290">該命令會傳回所有語音路由的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="3fb53-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="3fb53-291">身分識別： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="3fb53-291">Identity : LocalRoute</span></span>

<span data-ttu-id="3fb53-292">優先順序：0</span><span class="sxs-lookup"><span data-stu-id="3fb53-292">Priority : 0</span></span>

<span data-ttu-id="3fb53-293">描述：</span><span class="sxs-lookup"><span data-stu-id="3fb53-293">Description :</span></span>

<span data-ttu-id="3fb53-294">NumberPattern： ^ (\\ + 1 \[ 0-9 \] {10}) $</span><span class="sxs-lookup"><span data-stu-id="3fb53-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="3fb53-295">PstnUsages： {}</span><span class="sxs-lookup"><span data-stu-id="3fb53-295">PstnUsages : {}</span></span>

<span data-ttu-id="3fb53-296">PstnGatewayList： {}</span><span class="sxs-lookup"><span data-stu-id="3fb53-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="3fb53-297">名稱： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="3fb53-297">Name : LocalRoute</span></span>

<span data-ttu-id="3fb53-298">SuppressCallerId：</span><span class="sxs-lookup"><span data-stu-id="3fb53-298">SuppressCallerId :</span></span>

<span data-ttu-id="3fb53-299">AlternateCallerId：</span><span class="sxs-lookup"><span data-stu-id="3fb53-299">AlternateCallerId :</span></span>

<span data-ttu-id="3fb53-300">Lync Server 可讓您建立沒有 PSTN 使用方式的語音路由，也不會指定 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="3fb53-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="3fb53-301">不過，您實際上無法透過未設定這兩個屬性值的語音路由路由傳送呼叫。</span><span class="sxs-lookup"><span data-stu-id="3fb53-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="3fb53-302">因此，您可能會發現定期執行此命令會非常有用，它會傳回所有沒有 PSTN 使用狀況的語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="3fb53-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="3fb53-303">同樣地，此命令會傳回尚未設定為具有 PSTN 閘道之任何語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="3fb53-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="3fb53-304">檢查會議助理設定</span><span class="sxs-lookup"><span data-stu-id="3fb53-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="3fb53-305">檢查 PSTN 電話撥入式會議的會議照管設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="3fb53-306">會議助理設定只能使用 **Get-CsDialInConferencingConfiguration** Cmdlet 來檢索。</span><span class="sxs-lookup"><span data-stu-id="3fb53-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="3fb53-307">在 Lync Server 控制台中無法使用這些設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="3fb53-308">若要查看會議助理設定，請使用與下列類似的 Windows PowerShell 命令，以傳回全域會議應答設定的集合：</span><span class="sxs-lookup"><span data-stu-id="3fb53-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="3fb53-309">請注意，也可以在網站範圍設定會議助理設定。</span><span class="sxs-lookup"><span data-stu-id="3fb53-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="3fb53-310">若要傳回所有會議助理設定的資訊，請改用下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="3fb53-311">Get-CsDialInConferencingConfiguration Cmdlet 會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="3fb53-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="3fb53-312">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="3fb53-312">Identity : Global</span></span>

<span data-ttu-id="3fb53-313">EntryExitAnnouncementsType： UseNames</span><span class="sxs-lookup"><span data-stu-id="3fb53-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="3fb53-314">EnableNameRecording： True</span><span class="sxs-lookup"><span data-stu-id="3fb53-314">EnableNameRecording : True</span></span>

<span data-ttu-id="3fb53-315">EntryExitAnnouncementsEnabledByDefault： False</span><span class="sxs-lookup"><span data-stu-id="3fb53-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="3fb53-316">如果 EntryExitAnnouncementsEnabledByDefault 設定為 False，表示停用會議宣告。</span><span class="sxs-lookup"><span data-stu-id="3fb53-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="3fb53-317">若要啟用進入和關閉宣告，請執行類似下列的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="3fb53-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3fb53-318">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3fb53-318">See Also</span></span>


[<span data-ttu-id="3fb53-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="3fb53-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="3fb53-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="3fb53-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="3fb53-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="3fb53-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="3fb53-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3fb53-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="3fb53-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="3fb53-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="3fb53-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="3fb53-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="3fb53-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="3fb53-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="3fb53-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="3fb53-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3fb53-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

