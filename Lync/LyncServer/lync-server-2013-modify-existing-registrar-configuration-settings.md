---
title: Lync Server 2013：修改現有的註冊器設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29c01fd5af83c770844d05034baff5c3eb69e229
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bbbec-102">在 Lync Server 2013 中修改現有的註冊器設定設定</span><span class="sxs-lookup"><span data-stu-id="bbbec-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbbec-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bbbec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bbbec-104">您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="bbbec-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="bbbec-105">如需可用的通訊協定資訊，請參閱[在 Lync Server 2013 中建立註冊器設定設定](lync-server-2013-create-registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbec-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbbec-106">當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="bbbec-106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="bbbec-107">Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。</span><span class="sxs-lookup"><span data-stu-id="bbbec-107">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="bbbec-108">如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="bbbec-108">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="bbbec-109">如果企業使用者也會驗證服務器，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="bbbec-109">If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="bbbec-110">請遵循下列步驟來修改現有的註冊機。</span><span class="sxs-lookup"><span data-stu-id="bbbec-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bbbec-111">若要修改現有的註冊器配置設定</span><span class="sxs-lookup"><span data-stu-id="bbbec-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="bbbec-112">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bbbec-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bbbec-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bbbec-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bbbec-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbec-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bbbec-115">在左導覽列中，按一下 [**安全性**]，然後按一下 [**註冊**]。</span><span class="sxs-lookup"><span data-stu-id="bbbec-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="bbbec-116">在 [**註冊機構**] 頁面上，按一下服務，然後按一下 [**編輯**]，再按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="bbbec-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bbbec-117">在 [**編輯註冊機設定**] 中，依據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="bbbec-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="bbbec-118">**啟用 kerberos 驗證**讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。</span><span class="sxs-lookup"><span data-stu-id="bbbec-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="bbbec-119">**啟用 ntlm 驗證**讓集區中的伺服器使用 NTLM 時面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="bbbec-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="bbbec-120">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="bbbec-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="bbbec-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bbbec-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

