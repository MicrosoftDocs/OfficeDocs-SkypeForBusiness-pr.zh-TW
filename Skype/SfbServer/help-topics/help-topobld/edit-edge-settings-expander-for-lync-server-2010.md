---
title: Lync Server 2010 的編輯邊緣設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: '您可以設定下列屬性來編輯 Edge 伺服器或 Edge 池的設定:'
ms.openlocfilehash: 1b349d5640ea2debb4730ce262795616258b3475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189526"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2a48e-103">Lync Server 2010 的編輯邊緣設定擴展器</span><span class="sxs-lookup"><span data-stu-id="2a48e-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2a48e-104">您可以設定下列屬性來編輯 Edge 伺服器或 Edge 池的設定:</span><span class="sxs-lookup"><span data-stu-id="2a48e-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="2a48e-105">**一般**</span><span class="sxs-lookup"><span data-stu-id="2a48e-105">**General**</span></span>
  
- <span data-ttu-id="2a48e-106">**內部池 FQDN**: 內部池的完整功能變數名稱是 edge 伺服器或 edge 池的身分識別, 如在網域名稱系統 (DNS) 主機 (A 或 AAAA IPv6) 記錄中定義。</span><span class="sxs-lookup"><span data-stu-id="2a48e-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="2a48e-107">如果您想要將 Edge 伺服器或 Edge 池與其他會話初始通訊協定夥伴啟用聯盟, 請選取 **[針對此 Edge 池啟用同盟 (埠 5061)** ]。</span><span class="sxs-lookup"><span data-stu-id="2a48e-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2a48e-108">您只能針對同盟定義一台邊緣伺服器或邊緣池。</span><span class="sxs-lookup"><span data-stu-id="2a48e-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="2a48e-109">相關聯的螢幕擷取畫面中所顯示的設定會指出已針對同盟設定其他邊緣伺服器或邊緣池。</span><span class="sxs-lookup"><span data-stu-id="2a48e-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="2a48e-110">同盟 (_sipfederationtls) 的外部 DNS SRV 記錄 (_tcp)\< 。外部功能變數名稱\>) 會指向 [聯盟] 的邊緣伺服器或邊緣池。</span><span class="sxs-lookup"><span data-stu-id="2a48e-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="2a48e-111">預設情況下,**內部配置複製埠 (HTTPS)** 是在 TCP 埠4443上, 會複製中央管理儲存區的本機 (也就是本機的邊緣伺服器) 複本。</span><span class="sxs-lookup"><span data-stu-id="2a48e-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="2a48e-112">中央管理存放區的本機複本位於每一部電腦上的 SQL Server **RTCLOCAL**資料庫中。</span><span class="sxs-lookup"><span data-stu-id="2a48e-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="2a48e-113">從中央管理伺服器 (或擁有中央管理伺服器角色的前端伺服器或前端池) 開始, 到邊緣伺服器且是內部介面埠, 複製是單向的。</span><span class="sxs-lookup"><span data-stu-id="2a48e-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="2a48e-114">**下一個躍點選取**</span><span class="sxs-lookup"><span data-stu-id="2a48e-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="2a48e-115">選取您**下一個躍點數池**的清單。</span><span class="sxs-lookup"><span data-stu-id="2a48e-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="2a48e-116">您可以定義 Director、主管池、前端伺服器或前端池來擔當此角色。</span><span class="sxs-lookup"><span data-stu-id="2a48e-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="2a48e-117">下一個躍點池是伺服器或伺服器池, 可接受來自 Edge 伺服器或 Edge 池內部介面的入站 SIP 訊息, 並將輸出 SIP 傳送到 Edge 內部介面。</span><span class="sxs-lookup"><span data-stu-id="2a48e-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a48e-118">主管是一個選用的角色, 如果您決定不部署控制器, 前端伺服器 (單一電腦或池中) 會假設主管角色。</span><span class="sxs-lookup"><span data-stu-id="2a48e-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="2a48e-119">**外部設定**</span><span class="sxs-lookup"><span data-stu-id="2a48e-119">**External settings**</span></span>
  
<span data-ttu-id="2a48e-120">此區段的屬性可讓您編輯 Edge 伺服器或 Edge 池外部設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="2a48e-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="2a48e-121">下列屬性可供編輯:</span><span class="sxs-lookup"><span data-stu-id="2a48e-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="2a48e-122">如果您想要為每個 Edge 伺服器服務指派不同的 IP 位址及完整的功能變數名稱, 請選取 [**針對 web 會議與 A/V 啟用個別的 FQDN 和 IP 位址**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2a48e-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a48e-123">如果您選擇不選取此核取方塊, 則必須針對每個 Edge 服務使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="2a48e-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="2a48e-124">每個 Edge 服務都會共用為存取邊緣服務定義的 FQDN, 因此會使用相同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2a48e-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="2a48e-125">每個 Edge 服務必須由不同的 IP 位址和相同的埠, 或是相同的 IP 位址和唯一的埠值來唯一識別。</span><span class="sxs-lookup"><span data-stu-id="2a48e-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="2a48e-126">如果您想要將 A/V Edge 服務設定為使用私人位址或其他將隱藏在網路位址轉譯 (NAT) 裝置後面的位址, 請選取**a/v 邊緣服務**。</span><span class="sxs-lookup"><span data-stu-id="2a48e-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="2a48e-127">若要編輯**存取邊緣服務**, 請根據主機 (A 和 AAAA If 使用 IPv6) 中定義的存取邊緣服務定義**池 FQDN** , 並將埠值</span><span class="sxs-lookup"><span data-stu-id="2a48e-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="2a48e-128">若要編輯**網路會議 edge 服務**, 請根據主機 (a 和 AAAA if IPv6) 中的定義, 為網路會議 edge 服務定義一個**池 FQDN** (a), 並使用埠值</span><span class="sxs-lookup"><span data-stu-id="2a48e-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="2a48e-129">若要編輯**a/v 邊緣服務**, 請根據主機 (a 和 AAAA If 使用 IPv6) 的定義, 為 a/v edge 服務定義一個**池 FQDN** (a), 以及一個埠值</span><span class="sxs-lookup"><span data-stu-id="2a48e-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2a48e-130">如果您已選取 [**啟用 web 會議的個別 FQDN 和 IP 位址] 和 [A/V** ] 核取方塊, 則只有存取邊緣服務池 FQDN 可供編輯。</span><span class="sxs-lookup"><span data-stu-id="2a48e-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="2a48e-131">為三個邊緣服務中的每一個指派不同的埠。</span><span class="sxs-lookup"><span data-stu-id="2a48e-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="2a48e-132">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="2a48e-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2a48e-133">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="2a48e-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2a48e-134">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="2a48e-134">**Help** Displays this help screen.</span></span>
  

