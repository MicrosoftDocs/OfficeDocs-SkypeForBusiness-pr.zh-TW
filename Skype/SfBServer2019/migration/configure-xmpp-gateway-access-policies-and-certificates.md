---
title: 設定 XMPP 閘道存取原則及憑證
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。 XMPP 設定可讓使用者透過以下方式存取 XMPP 網域使用者：
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813761"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="0f7c0-104">設定 XMPP 閘道存取原則及憑證</span><span class="sxs-lookup"><span data-stu-id="0f7c0-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="0f7c0-105">XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="0f7c0-106">XMPP 設定可讓使用者透過以下方式存取 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="0f7c0-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="0f7c0-107">IM 和目前狀態-僅限人員的人員</span><span class="sxs-lookup"><span data-stu-id="0f7c0-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="0f7c0-108">在商務用 Skype 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="0f7c0-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="0f7c0-109">當您設定 XMPP 聯盟夥伴支援的原則時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者或 SIP 聯盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="0f7c0-110">您可以針對每個 XMPP 聯盟網域設定 XMPP 聯盟夥伴，以允許使用者新增連絡人並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="0f7c0-111">原則就緒之後，您必須設定 XMPP 閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0f7c0-112">在商務用 Skype Server 2019 中已棄用 XMPP 功能，但在舊版伺服器與商務用 Skype Server 2019 共存的情況下，仍可繼續使用。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="0f7c0-113">請確定您已部署舊版伺服器（商務用 Skype Server 2015/Lync Server 2013） XMPP 閘道，並將訪問原則設定為允許使用者使用舊版 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="0f7c0-114">如需詳細資訊，請參閱[遷移 XMPP 同盟](migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="0f7c0-115">設定外部存取原則，以允許使用者使用舊版 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="0f7c0-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="0f7c0-116">開啟舊版商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0f7c0-117">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="0f7c0-118">依序按一下 [新增]\*\*\*\* 和 [使用者原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="0f7c0-119">輸入外部存取使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="0f7c0-120">提供外部存取使用者原則的描述。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="0f7c0-121">選取 [**啟用與聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="0f7c0-122">選取 [**啟用與 XMPP 聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="0f7c0-123">按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="0f7c0-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

