---
title: Lync Server 2013： Lync Windows Store 應用程式需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="8d68d-102">Lync Server 2013 的 lync Windows Store 應用程式需求</span><span class="sxs-lookup"><span data-stu-id="8d68d-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d68d-103">_**主題上次修改日期：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="8d68d-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="8d68d-104">已部署 Lync Server 內部部署的組織必須符合下列需求才能支援 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8d68d-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d68d-105">針對 lync server 2010，請在所有伺服器上執行 lync server 2010 的累積更新：2月2012（適用于<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>）或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8d68d-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="8d68d-106">若要讓使用者加入會議，請在伺服器上執行 Lync Server 2010 的累積更新：10月2012（可在<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>）。</span><span class="sxs-lookup"><span data-stu-id="8d68d-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="8d68d-107">在伺服器上啟用 [自動探索]、[Lync Web App] 和 [Web 票證服務]。</span><span class="sxs-lookup"><span data-stu-id="8d68d-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="8d68d-108">在前端伺服器或前端池中啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="8d68d-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="8d68d-109">（前端伺服器或前端池的使用者註冊程式通常稱為註冊機）。如需詳細資訊，請參閱[在 Lync Server 2013 中建立註冊機構配置設定](lync-server-2013-create-registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="8d68d-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="8d68d-110">發佈自動探索服務的 DNS 別名（CNAME）資源記錄。</span><span class="sxs-lookup"><span data-stu-id="8d68d-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="8d68d-111">您不再需要確認頒發給 Lync 伺服器的憑證的憑證吊銷清單（CRL）發佈點（CDP）指向 HTTP 資源，而不是 LDAP 資源。</span><span class="sxs-lookup"><span data-stu-id="8d68d-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="8d68d-112">不過，請確認用戶端電腦已安裝最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="8d68d-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="8d68d-113">在企業中設定 HTTP proxy，以允許 Lync server 相關的 HTTP 流量。</span><span class="sxs-lookup"><span data-stu-id="8d68d-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="8d68d-114">如有需要，請為自動探索、Lync Web App 及 WebTicket 服務新增例外狀況。</span><span class="sxs-lookup"><span data-stu-id="8d68d-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="8d68d-115">在用戶端上，安裝 Windows 8.1 和最新版本的 Lync Windows Store 應用程式，修正通常在使用多個網域時發生的登入問題（例如，SIP URI 是**userA@domainZ.com** ，而 Edge 伺服器是**sip.domainX.com**）。</span><span class="sxs-lookup"><span data-stu-id="8d68d-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="8d68d-116">如果您的組織訂閱 Lync Online 或 Office 365，而且您使用自己的功能變數名稱，您必須採取一些額外步驟來設定您的網路，以便在 Lync 伺服器中自動尋找。</span><span class="sxs-lookup"><span data-stu-id="8d68d-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="8d68d-117">Lync Windows Store app 與行動裝置上的 Lync 的網路設定需求相同。</span><span class="sxs-lookup"><span data-stu-id="8d68d-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="8d68d-118">請依照 Office 365 wiki 文章「設定 Lync 行動裝置」（位於）中的指示設定您的網路[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)。</span><span class="sxs-lookup"><span data-stu-id="8d68d-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8d68d-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="8d68d-119">See Also</span></span>


[<span data-ttu-id="8d68d-120">在 Lync Server 2013 中部署 Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="8d68d-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

