---
title: 啟用或停用同盟協力廠商探索
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817423"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="fb701-103">啟用或停用商務用 Skype Server 中的同盟合作夥伴探索</span><span class="sxs-lookup"><span data-stu-id="fb701-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="fb701-104">當您部署 Edge Server 並為組織啟用同盟時，您應該會指定是否支援同盟協力廠商網域的自動探索。</span><span class="sxs-lookup"><span data-stu-id="fb701-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="fb701-105">使用本主題中的程式來變更該設定。</span><span class="sxs-lookup"><span data-stu-id="fb701-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="fb701-106">下列程式假設您已經為組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="fb701-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="fb701-107">如需啟用同盟的詳細資訊，請參閱 [啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="fb701-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="fb701-108">啟用或停用組織的自動探索同盟網域</span><span class="sxs-lookup"><span data-stu-id="fb701-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="fb701-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="fb701-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb701-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="fb701-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="fb701-111">在左導覽列中，按一下 [ **外部使用者存取**]，然後按一下 [ **Access Edge** 設定]。</span><span class="sxs-lookup"><span data-stu-id="fb701-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fb701-112">在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="fb701-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fb701-113">在 [ **編輯 Access Edge** 設定] 的 [ **啟用與同盟使用者的通訊**] 下，選取或清除 [ **啟用夥伴網域探索** ] 核取方塊，以啟用或停用自動探索夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="fb701-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="fb701-114">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="fb701-114">Click **Commit**.</span></span>

<span data-ttu-id="fb701-115">若要讓同盟使用者與商務用 Skype Server 部署中的使用者共同作業，您必須至少設定一個外部存取原則，以支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="fb701-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="fb701-116">如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="fb701-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="fb701-117">如需控制特定同盟網域存取權的詳細資訊，請參閱 [管理 sip 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 和 [管理 sip 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="fb701-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb701-118">使用 Windows PowerShell Cmdlet 來啟用或停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="fb701-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="fb701-119">同盟協力廠商的探索可使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="fb701-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="fb701-120">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb701-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="fb701-121">啟用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="fb701-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="fb701-122">若要啟用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="fb701-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="fb701-123">請注意，您必須啟用 DNS SRV 路由才能變更此屬性值。</span><span class="sxs-lookup"><span data-stu-id="fb701-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="fb701-124">停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="fb701-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="fb701-125">若要停用同盟協力廠商的探索，請將 **EnablePartnerDiscovery** 屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="fb701-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

