---
title: 設定 XMPP 閘道存取原則及憑證
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="5846a-102">設定 XMPP 閘道存取原則及憑證</span><span class="sxs-lookup"><span data-stu-id="5846a-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5846a-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="5846a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="5846a-104">XMPP 同盟會根據可擴展訊息和目前狀態通訊協定（XMPP）來定義外部部署。</span><span class="sxs-lookup"><span data-stu-id="5846a-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="5846a-105">XMPP 設定可讓 Lync 使用者透過以下方式存取 XMPP 網域使用者：</span><span class="sxs-lookup"><span data-stu-id="5846a-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="5846a-106">IM 和目前狀態-僅限人員的人員</span><span class="sxs-lookup"><span data-stu-id="5846a-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="5846a-107">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="5846a-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="5846a-108">當您針對可擴展訊息和目前狀態通訊協定（XMPP）同盟合作夥伴支援策略時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者的使用者（例如，Windows Live）或 SIP 聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="5846a-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="5846a-109">您可以針對每個 XMPP 聯盟網域設定 XMPP 聯盟夥伴，以允許使用者新增連絡人並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="5846a-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="5846a-110">原則就緒之後，您必須設定 XMPP 閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="5846a-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5846a-111">若要開始 XMPP 閘道遷移，您需要部署 Lync Server 2013 XMPP 閘道，並設定存取原則，以讓 Lync Server 2013 的使用者能夠 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="5846a-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="5846a-112">在執行這些步驟之前，必須先將所有使用者移至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="5846a-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="5846a-113">如需詳細資訊，請參閱<A href="configure-xmpp-gateway-on-lync-server-2013.md">在 Lync Server 2013 上設定 XMPP 閘道</A>。</span><span class="sxs-lookup"><span data-stu-id="5846a-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="5846a-114">設定外部存取原則，以允許使用者使用 Lync Server 2013 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="5846a-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="5846a-115">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="5846a-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="5846a-116">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="5846a-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="5846a-117">按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="5846a-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="5846a-118">輸入外部存取使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="5846a-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="5846a-119">提供外部存取使用者原則的描述。</span><span class="sxs-lookup"><span data-stu-id="5846a-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="5846a-120">選取 [**啟用與聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="5846a-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="5846a-121">選取 [**啟用與 XMPP 聯盟使用者的通訊**]。</span><span class="sxs-lookup"><span data-stu-id="5846a-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="5846a-122">按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="5846a-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

