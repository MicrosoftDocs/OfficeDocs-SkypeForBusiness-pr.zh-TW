---
title: Lync Server 2013：查看樹系的全域設定狀態
description: Lync Server 2013：查看樹系全域設定的狀態。
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
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567589"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="b1bc3-103">在 Lync Server 2013 中查看樹系全域設定的狀態</span><span class="sxs-lookup"><span data-stu-id="b1bc3-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1bc3-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b1bc3-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="b1bc3-105">管理員應該每月檢查 Lync Server 2013 部署的全域設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="b1bc3-106">目標是複查針對一組已知設定所實施的設定，這是一個基準設定，可協助保證設定有效，並判斷是否應該更新基準檔。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="b1bc3-107">對全域設定所做的變更應透過應包含記錄新設定的變更控制過程來實施。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="b1bc3-108">下列各節將說明應該檢查的全域設定：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="b1bc3-109">檢查一般設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-109">Check general settings</span></span>

<span data-ttu-id="b1bc3-110">檢查 [一般設定]，包括 Lync Server 2013 (SIP) 網域的支援的會話初始通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="b1bc3-111">SIP 網域資訊可使用 Windows PowerShell 和 **Get-CsSipDomain** Cmdlet 傳回。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="b1bc3-112">若要傳回此資訊，請執行 `Get-CsSipDomain` Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="b1bc3-113">Get-CsSipDomain 會針對所有已獲授權的 SIP 網域，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="b1bc3-114">身分識別名稱 IsDefault</span><span class="sxs-lookup"><span data-stu-id="b1bc3-114">Identity Name IsDefault</span></span>

<span data-ttu-id="b1bc3-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="b1bc3-115">\-------- ---- ---------</span></span>

<span data-ttu-id="b1bc3-116">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="b1bc3-117">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="b1bc3-118">如果 IsDefault 屬性設定為 True，對應的網域就是您的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="b1bc3-119">您可以使用 Set-CsSipDomain Cmdlet 變更組織的預設 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="b1bc3-120">不過，您不能只刪除預設的 SIP 網域，因為這會讓您沒有預設網域。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="b1bc3-121">如果您想要刪除 fabrikam.com 網域 (如先前範例) 所示，您必須先將 na.fabrikam.com 設定為您的預設網域。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="b1bc3-122">檢查會議設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-122">Check meeting settings</span></span>

<span data-ttu-id="b1bc3-123">會議設定包括會議原則定義，以及在會議中參與匿名使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="b1bc3-124">您可以使用 Windows PowerShell 和 **Get-CsMeetingConfiguration** Cmdlet 來找回會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="b1bc3-125">例如，下列命令會傳回全域會議設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="b1bc3-126">Get-CsMeetingConfiguration –身分識別 "Global" 會議設定設定也可以在網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="b1bc3-127">因此，您可能會想要使用下列命令，該命令會傳回所有會議設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="b1bc3-128">**Get-CsMeetingConfiguration** Cmdlet 會傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="b1bc3-129">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-129">Identity : Global</span></span>

<span data-ttu-id="b1bc3-130">PstnCallersBypassLobby： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="b1bc3-131">EnableAssignedConferenceType： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="b1bc3-132">DesignateAsPresenter：公司</span><span class="sxs-lookup"><span data-stu-id="b1bc3-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="b1bc3-133">AssignedConferenceTypeByDefault： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="b1bc3-134">AdmitAnonymousUsersByDefault： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="b1bc3-135">同樣地，清單中的最後一個專案會 **AdmitAnonymousUsersByDefault**，啟用或停用匿名使用者參與會議的功能。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="b1bc3-136">檢查會議設定時，您可能會發現比較目前設定與預設對等專案是很有用的。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="b1bc3-137">您可以執行下列命令來查看預設會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b1bc3-138">上一個命令會建立全域會議設定（僅限記憶體）實例的全域會議設定，此範例會使用每個屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="b1bc3-139">當您執行此命令時，並不會建立實際的會議設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="b1bc3-140">不過，所有的預設屬性值都會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="b1bc3-141">檢查 Edge Server 及其設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="b1bc3-142">您可以使用 Windows PowerShell 來找回 Edge Server 資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="b1bc3-143">此命令會傳回設定供組織使用之所有 Edge Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="b1bc3-144">傳回的資訊包含各 Edge Server 的所有 FQDN 和埠設定：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="b1bc3-145">Identity： Edgeserver atl-edge： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-146">註冊機構：報名者： LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-147">AccessEdgeInternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="b1bc3-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="b1bc3-148">AccessEdgeExternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="b1bc3-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="b1bc3-149">AccessEdgeClientPort：443</span><span class="sxs-lookup"><span data-stu-id="b1bc3-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="b1bc3-150">DataPsomServerPort：8057</span><span class="sxs-lookup"><span data-stu-id="b1bc3-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="b1bc3-151">DataPsomClientPort：444</span><span class="sxs-lookup"><span data-stu-id="b1bc3-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="b1bc3-152">MediaRelayAuthEdgePort：5062</span><span class="sxs-lookup"><span data-stu-id="b1bc3-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="b1bc3-153">MediaRelayAuthInternalTurnTcpPort：443</span><span class="sxs-lookup"><span data-stu-id="b1bc3-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="b1bc3-154">MediaRelayAuthExternalTurnTcpPort：445</span><span class="sxs-lookup"><span data-stu-id="b1bc3-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="b1bc3-155">MediaRelayAuthInternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="b1bc3-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="b1bc3-156">MediaRelayAuthExternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="b1bc3-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="b1bc3-157">MediaCommunicationPortStart：50000</span><span class="sxs-lookup"><span data-stu-id="b1bc3-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="b1bc3-158">MediaComunicationPortCount：10000</span><span class="sxs-lookup"><span data-stu-id="b1bc3-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="b1bc3-159">AccessEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-160">DataEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="b1bc3-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="b1bc3-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="b1bc3-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="b1bc3-163">ExternalMrasFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-164">DependentServiceList： {註冊機構： LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="b1bc3-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="b1bc3-165">ConferencingServer： LYNC-SE。 fabrikam</span><span class="sxs-lookup"><span data-stu-id="b1bc3-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="b1bc3-166">com，MediationServer： LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="b1bc3-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="b1bc3-167">fabrikam.com}</span></span>

<span data-ttu-id="b1bc3-168">ServiceId： fabrikam.com-Edgeserver atl-edge-2</span><span class="sxs-lookup"><span data-stu-id="b1bc3-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="b1bc3-169">SiteId：網站:fabrikam</span><span class="sxs-lookup"><span data-stu-id="b1bc3-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="b1bc3-170">PoolFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1bc3-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="b1bc3-171">版本：5</span><span class="sxs-lookup"><span data-stu-id="b1bc3-171">Version : 5</span></span>

<span data-ttu-id="b1bc3-172">角色： Edgeserver atl-edge</span><span class="sxs-lookup"><span data-stu-id="b1bc3-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="b1bc3-173">檢查同盟設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-173">Check federation settings</span></span>

<span data-ttu-id="b1bc3-174">檢查同盟設定，例如是否已設定，以及是否為「是」，FQDN 和埠。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="b1bc3-175">使用 Access Edge 設定的全域集合，啟用並停用同盟。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="b1bc3-176">此外，這些也意味著同盟設定為全部或無基準：已為整個組織啟用同盟，或對整個組織停用同盟</span><span class="sxs-lookup"><span data-stu-id="b1bc3-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="b1bc3-177">您可以使用 Windows PowerShell 傳回您的 Access Edge 設定設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="b1bc3-178">若要這麼做，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="b1bc3-179">接著，該命令會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="b1bc3-180">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-180">Identity : Global</span></span>

<span data-ttu-id="b1bc3-181">AllowAnonymousUsers： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="b1bc3-182">AllowFederatedUsers： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="b1bc3-183">AllowOutsideUsers： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="b1bc3-184">BeClearingHouse： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-184">BeClearingHouse : False</span></span>

<span data-ttu-id="b1bc3-185">EnablePartnerDiscovery： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="b1bc3-186">EnableArchivingDisclaimer： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="b1bc3-187">KeepCrlsUpToDateForPeers： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="b1bc3-188">MarkSourceVerifiableOnOutgoingMessages： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="b1bc3-189">OutgoingTlsCountForFederatedPartners：4</span><span class="sxs-lookup"><span data-stu-id="b1bc3-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="b1bc3-190">RoutingMethod： UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="b1bc3-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="b1bc3-191">如果 **AllowFederatedUsers** 屬性設定為 True，表示您的組織已啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="b1bc3-192"> (設定 **AllowFederatedUsers** 設定為 True 也表示，在分割網域案例中，您的內部部署使用者將能夠與您的雲端使用者無縫通訊。 ) </span><span class="sxs-lookup"><span data-stu-id="b1bc3-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="b1bc3-193">若要取得 Edge Server 的 FQDN 及埠設定，請參閱上一個工作 (Edge Server 及其設定) 。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="b1bc3-194">在全域範圍啟用同盟，只表示使用者可能會與同盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="b1bc3-195">若要判斷是否有任何個別使用者可以實際與同盟使用者通訊，需要檢查指派給該使用者的外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="b1bc3-196">您可以使用 Windows PowerShell 傳回外部使用者存取訊號。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="b1bc3-197">例如，下列命令會傳回全域外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="b1bc3-198">而且，此命令會傳回所有外部使用者存取原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="b1bc3-199">傳回的資訊將如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-199">The returned information will resemble this:</span></span>

<span data-ttu-id="b1bc3-200">身分識別： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-200">Identity : False</span></span>

<span data-ttu-id="b1bc3-201">描述：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-201">Description :</span></span>

<span data-ttu-id="b1bc3-202">EnableFederationAccess： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="b1bc3-203">EnablePublicCloudAccess： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="b1bc3-204">EnablePublicCloudAccessAudioVideoAccess： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="b1bc3-205">EnableOutsideAccess： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="b1bc3-206">如果 **EnableFederationAccess** 設定為 True，則指定原則所管理的使用者可以與同盟使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="b1bc3-207">檢查封存設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-207">Check archiving settings</span></span>

<span data-ttu-id="b1bc3-208">檢查內部及同盟通訊的封存設定。在驗證內部和外部封存的設定之前，您應該確認已啟用封存。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="b1bc3-209">您可以使用 Windows PowerShell 和 Get-CsArchivingConfiguration Cmdlet 來驗證封存設定設定：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="b1bc3-210">請注意，也可以在網站範圍中設定封存設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="b1bc3-211">若要傳回所有封存設定的資訊，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="b1bc3-212">Get-CsArchivingConfiguration Cmdlet 會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="b1bc3-213">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-213">Identity : Global</span></span>

<span data-ttu-id="b1bc3-214">EnableArchiving： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-214">EnableArchiving : False</span></span>

<span data-ttu-id="b1bc3-215">EnablePurging： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-215">EnablePurging : False</span></span>

<span data-ttu-id="b1bc3-216">PurgeExportedArchivesOnly： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="b1bc3-217">BlockOnArchiveFailure： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="b1bc3-218">KeepArchivingDataForDays：14</span><span class="sxs-lookup"><span data-stu-id="b1bc3-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="b1bc3-219">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="b1bc3-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="b1bc3-220">ArchiveDuplicateMessages： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="b1bc3-221">CachePurgingInterval：24</span><span class="sxs-lookup"><span data-stu-id="b1bc3-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="b1bc3-222">如果 EnableArchiving 屬性設定為 False，表示將不會封存任何通訊會話。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="b1bc3-223">如果您只想要封存立即訊息會話，請使用類似下列的命令來啟用 IM 會話的封存：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="b1bc3-224">若要封存會議會話和立即訊息會話，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="b1bc3-225">如果您想要將目前的封存設定與預設設定進行比較，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b1bc3-226">該命令會為全域封存設定設定建立僅限記憶體的實例。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="b1bc3-227">這不是 Lync Server 所使用之實際設定的集合。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="b1bc3-228">不過，它會顯示所有封存配置屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="b1bc3-229">您也可以使用此命令傳回封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="b1bc3-230">在您確認封存已啟用之後，您就可以查看封存原則，判斷是否要封存內部和外部通訊會話。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="b1bc3-231">您可以使用 Get-CsArchivingPolicy Cmdlet 來檢索封存原則資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="b1bc3-232">例如，下列命令會傳回全域封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="b1bc3-233">因為封存原則也可以在網站和個別使用者範圍內設定，所以您也可以使用此命令，傳回所有封存原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="b1bc3-234">您從 Get-CsArchivingPolicy 取得的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="b1bc3-235">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-235">Identity : Global</span></span>

<span data-ttu-id="b1bc3-236">描述：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-236">Description :</span></span>

<span data-ttu-id="b1bc3-237">ArchiveInternal： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-237">ArchiveInternal : False</span></span>

<span data-ttu-id="b1bc3-238">ArchiveExternal： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-238">ArchiveExternal : False</span></span>

<span data-ttu-id="b1bc3-239">請注意，預設會停用封存原則中的內部和外部封存。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="b1bc3-240">檢查 CDR 設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-240">Check CDR settings</span></span>

<span data-ttu-id="b1bc3-241">檢查 (CDR) 設定對等、會議及語音通話詳細資料記錄的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="b1bc3-242">您可以使用 **Get-CsCdrConfiguration** CMDLET 傳回 CDR 設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="b1bc3-243">例如，下列命令會傳回全域 CDR 設定設定集合的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="b1bc3-244">因為 CDR 也可以在網站範圍上進行設定，所以您也可能會想要執行此命令，以傳回所有 CDR 設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="b1bc3-245">Get-CsCdrConfiguration Cmdlet 會針對每個 CDR 設定設定的集合，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="b1bc3-246">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-246">Identity : Global</span></span>

<span data-ttu-id="b1bc3-247">EnableCDR： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-247">EnableCDR : True</span></span>

<span data-ttu-id="b1bc3-248">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-248">EnablePurging : True</span></span>

<span data-ttu-id="b1bc3-249">KeepCallDetailForDays：60</span><span class="sxs-lookup"><span data-stu-id="b1bc3-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="b1bc3-250">KeepErrorReportForDays：60</span><span class="sxs-lookup"><span data-stu-id="b1bc3-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="b1bc3-251">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="b1bc3-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="b1bc3-252">您可以透過使用 Get-CsQoEConfiguration Cmdlet，傳回 QoE 監視的類似資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="b1bc3-253">例如，下列命令會傳回全域 QoE 配置設定集合的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="b1bc3-254">此資訊會類似如下：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-254">That information will resemble this:</span></span>

<span data-ttu-id="b1bc3-255">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-255">Identity : Global</span></span>

<span data-ttu-id="b1bc3-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="b1bc3-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="b1bc3-257">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-257">EnablePurging : True</span></span>

<span data-ttu-id="b1bc3-258">KeepQoEDataForDays：60</span><span class="sxs-lookup"><span data-stu-id="b1bc3-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="b1bc3-259">PurgeHourOfDay：1</span><span class="sxs-lookup"><span data-stu-id="b1bc3-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="b1bc3-260">EnableExternalConsumer： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="b1bc3-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="b1bc3-261">ExternalConsumerName :</span></span>

<span data-ttu-id="b1bc3-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="b1bc3-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="b1bc3-263">EnableQoE： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-263">EnableQoE : True</span></span>

<span data-ttu-id="b1bc3-264">如果您想要將目前的 CDR 設定與預設 CDR 設定進行比較，可以執行下列命令來複查預設值：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b1bc3-265">同樣地，您可以使用下列命令來檢索 QoE 監視的預設值：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="b1bc3-266">您也可以執行下列命令，傳回監控伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="b1bc3-267">檢查語音設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-267">Check voice settings</span></span>

<span data-ttu-id="b1bc3-268">語音設定通常對系統管理員來說包含在語音原則和語音路由中：語音原則包含決定個別使用者的功能 (例如轉寄或轉接) 呼叫的功能）的設定，而語音路由會決定) 呼叫在 PSTN 間路由 (和呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="b1bc3-269">語音原則資訊可透過使用 Windows PowerShell 進行檢索。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="b1bc3-270">例如，下列命令會傳回有關通用語音原則的資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="b1bc3-271">而且此命令會傳回設定供組織使用之所有語音原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="b1bc3-272">Get-CsVoicePolicy Cmdlet 所傳回的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="b1bc3-273">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-273">Identity : Global</span></span>

<span data-ttu-id="b1bc3-274">PstnUsages： {}</span><span class="sxs-lookup"><span data-stu-id="b1bc3-274">PstnUsages : {}</span></span>

<span data-ttu-id="b1bc3-275">描述：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-275">Description :</span></span>

<span data-ttu-id="b1bc3-276">AllowSimulRing： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-276">AllowSimulRing : True</span></span>

<span data-ttu-id="b1bc3-277">AllowCallForwarding： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="b1bc3-278">AllowPSTNReRouting： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="b1bc3-279">名稱： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="b1bc3-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="b1bc3-280">EnableDelegation： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-280">EnableDelegation : True</span></span>

<span data-ttu-id="b1bc3-281">EnableTeamCall： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-281">EnableTeamCall : True</span></span>

<span data-ttu-id="b1bc3-282">EnableCallTransfer： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="b1bc3-283">EnableCallPark： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-283">EnableCallPark : False</span></span>

<span data-ttu-id="b1bc3-284">EnableMaliciousCallTracing： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="b1bc3-285">EnableBWPolicyOverride： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="b1bc3-286">PreventPSTNTollBypass： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="b1bc3-287">您也可以建立傳回語音原則子集的查詢。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="b1bc3-288">例如，此命令會傳回所有允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="b1bc3-289">而且，此命令會傳回所有不允許來電轉接的語音原則：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="b1bc3-290">在 [Windows PowerShell] 中，使用 Get-CsVoiceRouting Cmdlet 傳回語音路由的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="b1bc3-291">該命令會傳回所有語音路由的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="b1bc3-292">身分識別： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="b1bc3-292">Identity : LocalRoute</span></span>

<span data-ttu-id="b1bc3-293">優先順序：0</span><span class="sxs-lookup"><span data-stu-id="b1bc3-293">Priority : 0</span></span>

<span data-ttu-id="b1bc3-294">描述：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-294">Description :</span></span>

<span data-ttu-id="b1bc3-295">NumberPattern： ^ (\\ + 1 \[ 0-9 \] {10}) $</span><span class="sxs-lookup"><span data-stu-id="b1bc3-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="b1bc3-296">PstnUsages： {}</span><span class="sxs-lookup"><span data-stu-id="b1bc3-296">PstnUsages : {}</span></span>

<span data-ttu-id="b1bc3-297">PstnGatewayList： {}</span><span class="sxs-lookup"><span data-stu-id="b1bc3-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="b1bc3-298">名稱： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="b1bc3-298">Name : LocalRoute</span></span>

<span data-ttu-id="b1bc3-299">SuppressCallerId：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-299">SuppressCallerId :</span></span>

<span data-ttu-id="b1bc3-300">AlternateCallerId：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-300">AlternateCallerId :</span></span>

<span data-ttu-id="b1bc3-301">Lync Server 可讓您建立沒有 PSTN 使用方式的語音路由，也不會指定 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="b1bc3-302">不過，您實際上無法透過未設定這兩個屬性值的語音路由路由傳送呼叫。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="b1bc3-303">因此，您可能會發現定期執行此命令會非常有用，它會傳回所有沒有 PSTN 使用狀況的語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="b1bc3-304">同樣地，此命令會傳回尚未設定為具有 PSTN 閘道之任何語音路由的身分識別：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="b1bc3-305">檢查會議助理設定</span><span class="sxs-lookup"><span data-stu-id="b1bc3-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="b1bc3-306">檢查 PSTN 電話撥入式會議的會議照管設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="b1bc3-307">會議助理設定只能使用 **Get-CsDialInConferencingConfiguration** Cmdlet 來檢索。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="b1bc3-308">在 Lync Server 控制台中無法使用這些設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="b1bc3-309">若要查看會議助理設定，請使用與下列類似的 Windows PowerShell 命令，以傳回全域會議應答設定的集合：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="b1bc3-310">請注意，也可以在網站範圍設定會議助理設定。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="b1bc3-311">若要傳回所有會議助理設定的資訊，請改用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="b1bc3-312">Get-CsDialInConferencingConfiguration Cmdlet 會傳回類似以下的資料：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="b1bc3-313">身分識別：全域</span><span class="sxs-lookup"><span data-stu-id="b1bc3-313">Identity : Global</span></span>

<span data-ttu-id="b1bc3-314">EntryExitAnnouncementsType： UseNames</span><span class="sxs-lookup"><span data-stu-id="b1bc3-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="b1bc3-315">EnableNameRecording： True</span><span class="sxs-lookup"><span data-stu-id="b1bc3-315">EnableNameRecording : True</span></span>

<span data-ttu-id="b1bc3-316">EntryExitAnnouncementsEnabledByDefault： False</span><span class="sxs-lookup"><span data-stu-id="b1bc3-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="b1bc3-317">如果 EntryExitAnnouncementsEnabledByDefault 設定為 False，表示停用會議宣告。</span><span class="sxs-lookup"><span data-stu-id="b1bc3-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="b1bc3-318">若要啟用進入和關閉宣告，請執行類似下列的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="b1bc3-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1bc3-319">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1bc3-319">See Also</span></span>


[<span data-ttu-id="b1bc3-320">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="b1bc3-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="b1bc3-321">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="b1bc3-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="b1bc3-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="b1bc3-323">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="b1bc3-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="b1bc3-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="b1bc3-325">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="b1bc3-326">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="b1bc3-327">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="b1bc3-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="b1bc3-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="b1bc3-329">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="b1bc3-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="b1bc3-330">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b1bc3-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

