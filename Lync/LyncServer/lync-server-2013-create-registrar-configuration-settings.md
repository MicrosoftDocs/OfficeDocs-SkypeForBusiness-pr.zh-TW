---
title: Lync Server 2013：建立註冊機配置設定
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
ms.openlocfilehash: bf2f9eac959e9061e42bdc05982593c9f21aa2b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="435ca-102">在 Lync Server 2013 中建立註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="435ca-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="435ca-103">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="435ca-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="435ca-104">您可以使用註冊機構來設定 proxy 伺服器驗證方法。</span><span class="sxs-lookup"><span data-stu-id="435ca-104">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="435ca-105">您指定的驗證通訊協定會決定集區中的伺服器在用戶端上面臨的挑戰類型。</span><span class="sxs-lookup"><span data-stu-id="435ca-105">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="435ca-106">可用的通訊協定包括：</span><span class="sxs-lookup"><span data-stu-id="435ca-106">The available protocols are:</span></span>

  - <span data-ttu-id="435ca-107">**Kerberos**    這是可供用戶端使用的最強式密碼型驗證配置，但通常只適用于企業用戶端，因為它需要用戶端連線至金鑰發佈中心 (Kerberos 網域控制站) 。</span><span class="sxs-lookup"><span data-stu-id="435ca-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="435ca-108">此設定適用于伺服器只驗證企業用戶端的情況。</span><span class="sxs-lookup"><span data-stu-id="435ca-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="435ca-109">**NTLM**    這是以密碼為基礎的驗證，可供在密碼上使用挑戰回應雜湊配置的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="435ca-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="435ca-110">這是唯一可供用戶端使用的驗證表單，但不連接到金鑰發佈中心 (Kerberos 網域控制站) （例如遠端使用者）。</span><span class="sxs-lookup"><span data-stu-id="435ca-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="435ca-111">如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。</span><span class="sxs-lookup"><span data-stu-id="435ca-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="435ca-112">**憑證驗證**    當伺服器需要從 Lync Phone Edition 用戶端、公共區域電話、Lync 2013 和 Lync Windows Store 應用程式取得憑證時，這是一種新的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="435ca-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="435ca-113">在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼 (PIN) 來成功驗證之後，Lync Server 2013 接著會布建 SIP URI 至電話，並布建 Lync Server 簽署憑證或識別 Joe (Ex： SN=joe@contoso.com ) 至電話的使用者憑證。</span><span class="sxs-lookup"><span data-stu-id="435ca-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="435ca-114">此憑證用來驗證註冊機構和 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="435ca-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="435ca-115">當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="435ca-115">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="435ca-116">Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。</span><span class="sxs-lookup"><span data-stu-id="435ca-116">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="435ca-117">如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="435ca-117">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="435ca-118">如果企業使用者也會驗證服務器，則會使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="435ca-118">If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="435ca-119">如果您要使用 Lync Windows Store 應用程式用戶端，則必須啟用憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="435ca-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="435ca-120">請遵循下列步驟建立新的註冊機。</span><span class="sxs-lookup"><span data-stu-id="435ca-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="435ca-121">若要建立新的註冊機配置設定</span><span class="sxs-lookup"><span data-stu-id="435ca-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="435ca-122">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="435ca-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="435ca-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="435ca-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="435ca-124">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="435ca-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="435ca-125">在左導覽列中，按一下 [**安全性**]，然後按一下 [**註冊**]。</span><span class="sxs-lookup"><span data-stu-id="435ca-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="435ca-126">在 [**註冊機**] 頁面上，按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="435ca-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="435ca-127">在 [**選取服務**] 中，按一下要套用註冊器的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="435ca-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="435ca-128">在 [**新註冊機] 設定**中，根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：</span><span class="sxs-lookup"><span data-stu-id="435ca-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="435ca-129">**啟用 kerberos 驗證**讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。</span><span class="sxs-lookup"><span data-stu-id="435ca-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="435ca-130">**啟用 ntlm 驗證**讓集區中的伺服器使用 NTLM 時面臨挑戰。</span><span class="sxs-lookup"><span data-stu-id="435ca-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="435ca-131">[**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。</span><span class="sxs-lookup"><span data-stu-id="435ca-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="435ca-132">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="435ca-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

