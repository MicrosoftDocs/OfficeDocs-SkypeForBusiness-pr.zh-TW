---
title: Lync Server 2013：定義 Survivable 分支裝置或伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329fae20f239f10583b83b64d9b78fa953f6cdc3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="eaf36-102">在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器</span><span class="sxs-lookup"><span data-stu-id="eaf36-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaf36-103">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="eaf36-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="eaf36-104">如果您將 Survivable Branch Appliance 或 Server 加入拓撲時尚未予以定義，請在中央網站執行下列程序。</span><span class="sxs-lookup"><span data-stu-id="eaf36-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="eaf36-105">若要定義 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="eaf36-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="eaf36-106">依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="eaf36-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eaf36-107">在主控台樹中，展開中央網站，展開 [**分支網站**]，然後展開您計畫部署 Survivable branch 裝置或 Survivable branch 伺服器的分支網站名稱。</span><span class="sxs-lookup"><span data-stu-id="eaf36-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="eaf36-108">以滑鼠右鍵按一下 [ **Survivable 分支裝置**]，然後按一下 [**新增 Survivable Branch 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="eaf36-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eaf36-109"><STRONG>Survivable 分支裝置</STRONG>是您用來定義 Survivable 分支伺服器和 Survivable 分支裝置的所在位置。</span><span class="sxs-lookup"><span data-stu-id="eaf36-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="eaf36-110">在 [**定義 Survivable 分支裝置**] 對話方塊中，按一下 [ **FQDN**]，然後輸入您要在此分支網站上部署之 Survivable Branch 裝置或 Survivable 分支伺服器的完整功能變數名稱 (FQDN) ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="eaf36-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eaf36-111">如果您要定義 Survivable 分支裝置，您在<STRONG>FQDN</STRONG>中輸入的名稱，必須與您指派給<STRONG>ServicePrincipalName</STRONG>屬性的 Survivable 分支裝置 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="eaf36-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="eaf36-112">如需詳細資訊，請參閱<A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch 裝置 To Active Directory In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="eaf36-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="eaf36-113">按一下 [**前端集**區]，在此 Survivable Branch 裝置或 Survivable branch 伺服器將要連線的中央網站上，按一下 [前端伺服器 (使用者服務集區) ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="eaf36-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="eaf36-114">按一下 [ **Edge Server**]，按一下此 Survivable branch 裝置或 Survivable branch 伺服器將要連線的 Edge 集區，以提供 PSTN 連線至分支網站的遠端使用者，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="eaf36-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="eaf36-115">按一下 [**閘道 FQDN 或 IP 位址**]，然後輸入 Survivable Branch 裝置或 Survivable Branch Server 關聯的閘道對等機的 FQDN 或 IP 位址，以進行路由傳送撥入或撥出的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="eaf36-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eaf36-116">如果您是在定義 Survivable Branch Appliance，此為 Survivable Branch Appliance 內之中繼伺服器將會連線以進行 PSTN 連線功能的閘道。</span><span class="sxs-lookup"><span data-stu-id="eaf36-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="eaf36-117">按一下 **[IP/PSTN 閘道的聆聽連接埠]**，接受預設連接埠。</span><span class="sxs-lookup"><span data-stu-id="eaf36-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="eaf36-118">在 [ **Sip 傳輸通訊協定**] 中，按一下 [Survivable 分支裝置] 或 [Survivable] 分支伺服器將要使用的傳輸通訊協定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="eaf36-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eaf36-119">基於安全考量，強烈建議您使用傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="eaf36-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="eaf36-120">如果您是在定義 Survivable Branch Appliance，請參閱您的 Survivable Branch Appliance 廠商文件，確認您的 Survivable Branch Appliance 支援 TLS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="eaf36-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="eaf36-121">在主控台樹狀目錄中，以滑鼠右鍵按一下新的 Survivable Branch Appliance 或 Server、按一下 **[拓撲]**，然後按一下 **[發行]**。</span><span class="sxs-lookup"><span data-stu-id="eaf36-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="eaf36-122">**後續步驟**：[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-分支網站](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)工作</span><span class="sxs-lookup"><span data-stu-id="eaf36-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

