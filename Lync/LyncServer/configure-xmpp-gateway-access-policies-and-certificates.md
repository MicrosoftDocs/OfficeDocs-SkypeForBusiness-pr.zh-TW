---
title: 設定 XMPP 閘道的存取原則和憑證
description: 設定 XMPP 閘道存取原則和憑證。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549709"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="16fca-103">設定 XMPP 閘道的存取原則和憑證</span><span class="sxs-lookup"><span data-stu-id="16fca-103">Configure XMPP gateway access policies and certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16fca-104">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="16fca-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="16fca-105">XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定 (XMPP) 來定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="16fca-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="16fca-106">XMPP 設定可讓 Lync 使用者依下列方式存取 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="16fca-106">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="16fca-107">IM 和目前狀態–僅限人員</span><span class="sxs-lookup"><span data-stu-id="16fca-107">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="16fca-108">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="16fca-108">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="16fca-109">當您設定支援可延伸訊息和目前狀態通訊協定 (XMPP) 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用至工作階段初始通訊協定 (SIP) 立即訊息 (IM) 服務提供者 (例如 Windows Live) 或 SIP 同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="16fca-109">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="16fca-110">您可以為每個 XMPP 同盟網域設定所需的 XMPP 同盟協力廠商，以讓使用者新增連絡人並與連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="16fca-110">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="16fca-111">原則就緒後，您必須設定 XMPP 閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="16fca-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16fca-112">若要開始 XMPP 閘道遷移，您必須部署 Lync Server 2013 XMPP 閘道，並設定存取原則以啟用 Lync Server 2013 XMPP 閘道的使用者。</span><span class="sxs-lookup"><span data-stu-id="16fca-112">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="16fca-113">在您執行這些步驟之前，必須先將所有使用者移至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="16fca-113">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="16fca-114">如需詳細資訊，請參閱 <A href="configure-xmpp-gateway-on-lync-server-2013.md">CONFIGURE XMPP gateway On Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="16fca-114">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="16fca-115">設定外部存取原則，以啟用使用者的 Lync Server 2013 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="16fca-115">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="16fca-116">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="16fca-116">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="16fca-117">在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="16fca-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="16fca-118">按一下 [ **新增** ]，然後按一下 [ **使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="16fca-118">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="16fca-119">輸入外部存取使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="16fca-119">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="16fca-120">提供外部存取使用者原則的描述。</span><span class="sxs-lookup"><span data-stu-id="16fca-120">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="16fca-121">選取 [啟用與同盟使用者的通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16fca-121">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="16fca-122">選取 [啟用與 XMPP 同盟使用者的通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16fca-122">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="16fca-123">按一下 [認可]\*\*\*\* 以儲存對網站或使用者原則的變更。</span><span class="sxs-lookup"><span data-stu-id="16fca-123">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

