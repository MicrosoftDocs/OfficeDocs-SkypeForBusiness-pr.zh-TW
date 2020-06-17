---
title: 設定 XMPP 閘道的存取原則和憑證
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定（XMPP）定義外部部署。 XMPP 設定可讓使用者依下列方式存取 XMPP 網域使用者：
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753933"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="a038d-104">設定 XMPP 閘道的存取原則和憑證</span><span class="sxs-lookup"><span data-stu-id="a038d-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="a038d-105">XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定（XMPP）定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="a038d-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="a038d-106">XMPP 設定可讓使用者依下列方式存取 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="a038d-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="a038d-107">IM 和目前狀態-僅限人員</span><span class="sxs-lookup"><span data-stu-id="a038d-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="a038d-108">在商務用 Skype 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="a038d-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="a038d-109">當您設定支援 XMPP 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用到會話初始通訊協定（SIP）立即訊息（IM）服務提供者或 SIP 同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="a038d-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="a038d-110">您可以為每個 XMPP 同盟網域設定 XMPP 同盟協力廠商，讓您的使用者能夠新增連絡人及與其通訊。</span><span class="sxs-lookup"><span data-stu-id="a038d-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="a038d-111">原則就緒後，您必須設定 XMPP 閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="a038d-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a038d-112">XMPP 功能在商務用 Skype Server 2019 中已被取代，但可以繼續使用與商務用 Skype Server 2019 共存的舊版伺服器。</span><span class="sxs-lookup"><span data-stu-id="a038d-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="a038d-113">請確認您已部署舊版伺服器（商務用 Skype Server 2015/Lync Server 2013） XMPP 閘道，並設定存取原則以啟用舊版 XMPP 閘道的使用者。</span><span class="sxs-lookup"><span data-stu-id="a038d-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="a038d-114">如需詳細資訊，請參閱[遷移 XMPP 同盟](migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="a038d-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="a038d-115">設定外部存取原則以允許使用者使用舊版 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="a038d-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="a038d-116">開啟舊版商務用 Skype Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a038d-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a038d-117">在左導覽列中，按一下 [**同盟和外部存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="a038d-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="a038d-118">依序按一下 **[新增]** 和 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="a038d-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="a038d-119">輸入外部存取使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="a038d-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="a038d-120">提供外部存取使用者原則的描述。</span><span class="sxs-lookup"><span data-stu-id="a038d-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="a038d-121">選取 [啟用與同盟使用者的通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a038d-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="a038d-122">選取 [啟用與 XMPP 同盟使用者的通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a038d-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="a038d-123">按一下 [認可]\*\*\*\* 以儲存對網站或使用者原則的變更。</span><span class="sxs-lookup"><span data-stu-id="a038d-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

