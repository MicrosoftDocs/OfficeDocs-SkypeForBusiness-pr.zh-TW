---
title: 啟用或停用探索同盟協力廠商
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818394"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="ad3cf-103">在商務用 Skype Server 中啟用或停用同盟合作夥伴的發現功能</span><span class="sxs-lookup"><span data-stu-id="ad3cf-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="ad3cf-104">當您部署您的 Edge 伺服器並為貴組織啟用同盟時，您應該已指定是否支援聯盟夥伴網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="ad3cf-105">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="ad3cf-106">下列程式假設您已經為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="ad3cf-107">如需啟用同盟的詳細資料，請參閱[啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="ad3cf-108">若要啟用或停用貴組織的聯盟網域自動探索</span><span class="sxs-lookup"><span data-stu-id="ad3cf-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="ad3cf-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ad3cf-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="ad3cf-111">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="ad3cf-112">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ad3cf-113">在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**啟用合作夥伴網域探索**] 核取方塊，以啟用或停用合作夥伴網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="ad3cf-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-114">Click **Commit**.</span></span>

<span data-ttu-id="ad3cf-115">若要讓聯盟使用者在商務用 Skype Server 部署中與使用者共同作業，您必須至少已將一個外部存取原則設定為支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="ad3cf-116">如需詳細資訊，請參閱[啟用或停用同盟與公用 IM](enable-or-disable-federation-and-public-im-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="ad3cf-117">如需控制特定聯盟網域存取權的詳細資料，請參閱[管理 sip 聯盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 sip 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ad3cf-118">使用 Windows PowerShell Cmdlet 來啟用或停用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="ad3cf-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ad3cf-119">同盟合作夥伴的探索可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 進行管理。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="ad3cf-120">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="ad3cf-121">若要啟用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="ad3cf-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="ad3cf-122">若要啟用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="ad3cf-123">請注意，您必須啟用 DNS SRV 路由才能變更這個屬性值。</span><span class="sxs-lookup"><span data-stu-id="ad3cf-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="ad3cf-124">若要停用同盟合作夥伴的探索</span><span class="sxs-lookup"><span data-stu-id="ad3cf-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="ad3cf-125">若要停用同盟合作夥伴的發現，請將**EnablePartnerDiscovery**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="ad3cf-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

