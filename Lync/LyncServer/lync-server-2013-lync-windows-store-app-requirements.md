---
title: Lync Server 2013： Lync Windows Store 應用程式需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3707c0074425411353a22b51d62251d33a4e31fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534600"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="d1bd0-102">Lync Server 2013 的 lync Windows 應用程式需求</span><span class="sxs-lookup"><span data-stu-id="d1bd0-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1bd0-103">_**主題上次修改日期：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="d1bd0-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="d1bd0-104">具有 Lync Server 內部部署的組織必須符合下列需求，才能支援 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1bd0-105">針對 Lync Server 2010，請執行 Lync Server 2010 的累計更新：2月 2012 (，可在<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp 2670352</A>) 或更新版本的所有伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="d1bd0-106">若要讓使用者加入會議，請在伺服器上執行 Lync Server 2010：十月 2012 (的累計更新<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; 3052&kbid = 2737915</A>) 。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="d1bd0-107">在伺服器上啟用自動探索、Lync Web App 及 Web 票據服務。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="d1bd0-108">在前端伺服器或前端集區上啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d1bd0-109"> (前端伺服器或前端集區上的使用者註冊程式通常稱為註冊機構。 ) 如需詳細資訊，請參閱 Create registration [configuration settings In Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="d1bd0-110">針對自動探索服務，發佈 DNS 別名 (CNAME) 資源記錄。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="d1bd0-111">您不再需要確定憑證吊銷清單 (CRL) 發佈點)  (設定為 Lync server 指向 HTTP 資源的憑證，而不是 LDAP 資源。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="d1bd0-112">不過，請確定用戶端電腦已安裝最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="d1bd0-113">設定企業中的 HTTP proxy，以允許 Lync server 相關的 HTTP 流量。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="d1bd0-114">如有必要，新增自動探索、Lync Web App 和 WebTicket 服務的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="d1bd0-115">在用戶端上，安裝 Windows 8.1 和最新版的 Lync Windows Store 應用程式，修正一般會在使用多個網域時發生的登入問題 (例如，當 SIP URI 是 **userA@domainZ.com** ，但 Edge Server 是 **sip.domainX.com**) 時。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="d1bd0-116">如果您的組織訂閱 Lync Online 或 Microsoft 365，而且您使用自己的功能變數名稱，則必須採取一些額外的步驟來設定您的網路，以便自動探索 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-116">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="d1bd0-117">在行動裝置上，Lync Windows Store 應用程式和 Lync 的網路設定需求相同。</span><span class="sxs-lookup"><span data-stu-id="d1bd0-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d1bd0-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d1bd0-118">See Also</span></span>


[<span data-ttu-id="d1bd0-119">在 Lync Server 2013 中部署 Lync Windows 應用商店應用程式</span><span class="sxs-lookup"><span data-stu-id="d1bd0-119">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
