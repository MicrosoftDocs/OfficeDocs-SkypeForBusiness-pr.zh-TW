---
title: Lync Server 2013：建立新的 Web 服務設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86105e4dbf6b624f87844a68ebe5fca6bba02247
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1ceec-102">在 Lync Server 2013 中建立新的 Web 服務配置設定</span><span class="sxs-lookup"><span data-stu-id="1ceec-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ceec-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1ceec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1ceec-104">您可以使用 [ **Web 服務**] 頁面來設定存取 Lync Server 2013 相關 web 伺服器與 web 服務的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="1ceec-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="1ceec-105">請按照這些步驟建立新的 Web 服務原則。</span><span class="sxs-lookup"><span data-stu-id="1ceec-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="1ceec-106">若要建立新的 web 服務設定</span><span class="sxs-lookup"><span data-stu-id="1ceec-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="1ceec-107">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1ceec-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1ceec-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1ceec-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ceec-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1ceec-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ceec-110">在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **Web 服務**]。</span><span class="sxs-lookup"><span data-stu-id="1ceec-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="1ceec-111">在 [ **Web 服務**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1ceec-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="1ceec-112">若要設定網站的 Web 服務，請按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="1ceec-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="1ceec-113">在 [**選取網站**] 中，按一下要將 Web 服務原則套用到哪個網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ceec-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="1ceec-114">若要設定文件庫的 Web 服務，請按一下 [**池配置**]。</span><span class="sxs-lookup"><span data-stu-id="1ceec-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="1ceec-115">在 [**選取服務**] 中，按一下將套用 Web 服務原則的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ceec-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="1ceec-116">在 [**新增 Web 服務**] 中，在**整合的 windows 驗證**中，選取 [**協商**]、[**整合式 windows 驗證**] 或 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="1ceec-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="1ceec-117">根據您的環境中用戶端和支援的功能，選取下列一或多個專案：</span><span class="sxs-lookup"><span data-stu-id="1ceec-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="1ceec-118">**啟用 Pin 驗證**，讓用戶端使用 pin 碼進行驗證。</span><span class="sxs-lookup"><span data-stu-id="1ceec-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="1ceec-119">**啟用憑證驗證**，將池中的伺服器頒發憑證給用戶端。</span><span class="sxs-lookup"><span data-stu-id="1ceec-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="1ceec-120">**啟用憑證連結下載**，讓伺服器提供驗證憑證下載該憑證的憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="1ceec-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="1ceec-121">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ceec-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

