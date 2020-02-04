---
title: Lync Server 2013：建立註冊機構配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8af28-102">在 Lync Server 2013 中建立註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="8af28-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8af28-103">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="8af28-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="8af28-104">您可以使用註冊機構來設定 proxy 伺服器驗證方法。</span><span class="sxs-lookup"><span data-stu-id="8af28-104">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="8af28-105">您指定的驗證通訊協定決定了將池中的伺服器問題到用戶端所面臨的挑戰類型。</span><span class="sxs-lookup"><span data-stu-id="8af28-105">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="8af28-106">可用的通訊協定包括：</span><span class="sxs-lookup"><span data-stu-id="8af28-106">The available protocols are:</span></span>

  - <span data-ttu-id="8af28-107">**Kerberos**   這是用戶端可用的最強式密碼驗證配置，但通常只有企業用戶端才能使用，因為它需要用戶端連線到金鑰發佈中心（Kerberos 網網域控制站）。</span><span class="sxs-lookup"><span data-stu-id="8af28-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="8af28-108">此設定適用于伺服器只驗證企業用戶端的情況。</span><span class="sxs-lookup"><span data-stu-id="8af28-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="8af28-109">**NTLM**   這是在密碼上使用質詢回應雜湊配置的用戶端提供的密碼式驗證。</span><span class="sxs-lookup"><span data-stu-id="8af28-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="8af28-110">這是不需連線到金鑰發佈中心（Kerberos 網網域控制站）（例如遠端使用者）的用戶端可使用的唯一驗證形式。</span><span class="sxs-lookup"><span data-stu-id="8af28-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="8af28-111">如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。</span><span class="sxs-lookup"><span data-stu-id="8af28-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="8af28-112">**憑證驗證**   當伺服器需要從 Lync Phone Edition 用戶端、常用的區域手機、lync 2013 和 lync Windows Store 應用程式取得憑證時，這是新的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="8af28-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="8af28-113">在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼（PIN）來成功驗證之後，Lync Server 2013 接著將 SIP URI 提供給手機，並將識別 Joe （Ex： SN=joe@contoso.com）的使用者憑證提供給手機。</span><span class="sxs-lookup"><span data-stu-id="8af28-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="8af28-114">這個憑證是用來向註冊機構和 Web 服務進行驗證。</span><span class="sxs-lookup"><span data-stu-id="8af28-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8af28-115">我們建議您在伺服器同時支援遠端與企業用戶端的驗證時，同時啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="8af28-115">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="8af28-116">邊緣伺服器與內部伺服器通訊，以確保只提供 NTLM 驗證給遠端用戶端。</span><span class="sxs-lookup"><span data-stu-id="8af28-116">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="8af28-117">如果在這些伺服器上只啟用 Kerberos，就無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="8af28-117">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="8af28-118">如果企業使用者也要針對伺服器進行驗證，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="8af28-118">If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="8af28-119">如果您要使用 Lync Windows Store app 用戶端，您必須啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="8af28-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="8af28-120">請依照這些步驟來建立新的註冊機構。</span><span class="sxs-lookup"><span data-stu-id="8af28-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="8af28-121">建立新的註冊機構配置設定</span><span class="sxs-lookup"><span data-stu-id="8af28-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="8af28-122">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8af28-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="8af28-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8af28-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8af28-124">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8af28-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8af28-125">在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。</span><span class="sxs-lookup"><span data-stu-id="8af28-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="8af28-126">在 [**註冊機**] 頁面上，按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="8af28-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="8af28-127">在 [**選取服務**] 中，按一下要套用註冊機構的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8af28-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="8af28-128">在 [**新的註冊機構設定**] 中，根據您的環境中用戶端和支援的功能，選取下列一或多個專案：</span><span class="sxs-lookup"><span data-stu-id="8af28-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="8af28-129">使用 Kerberos 驗證來**啟用 kerberos 驗證**，讓伺服器在池中有問題的挑戰。</span><span class="sxs-lookup"><span data-stu-id="8af28-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="8af28-130">**啟用 ntlm 驗證**，以讓池中的伺服器面臨使用 NTLM 的問題。</span><span class="sxs-lookup"><span data-stu-id="8af28-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="8af28-131">**啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。</span><span class="sxs-lookup"><span data-stu-id="8af28-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="8af28-132">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8af28-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

