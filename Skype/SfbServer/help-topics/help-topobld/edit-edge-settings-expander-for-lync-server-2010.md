---
title: 編輯 Edge 設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 您可以透過設定下列屬性來編輯 Edge Server 或 Edge 集區的設定：
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216114"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1eb0b-103">編輯 Edge 設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="1eb0b-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="1eb0b-104">您可以透過設定下列屬性來編輯 Edge Server 或 Edge 集區的設定：</span><span class="sxs-lookup"><span data-stu-id="1eb0b-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="1eb0b-105">**一般**</span><span class="sxs-lookup"><span data-stu-id="1eb0b-105">**General**</span></span>
  
- <span data-ttu-id="1eb0b-106">**內部集區 FQDN**：內部集區完整功能變數名稱為 edge Server 或 edge 集區的身分識別，如網域名稱系統中所定義的 (DNS) 主機 (A 或 AAAA 為 IPv6) 記錄。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="1eb0b-107">如果您想要啟用 Edge Server 或 Edge 集區以進行與其他會話初始通訊協定夥伴的同盟，請選取 [ \*\*啟用此 Edge 集區的同盟 (埠 5061) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1eb0b-108">您只能為同盟定義一部 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="1eb0b-109">關聯的螢幕擷取畫面所顯示的設定會指出已經為同盟設定其他 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="1eb0b-110">同盟 (_sipfederationtls ._tcp 的外部 DNS SRV 記錄。 \<external domain name\>) 會指向同盟的 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="1eb0b-111">內部設定複寫 \*\*埠 (HTTPS) \*\*（預設在 TCP 埠4443上）是本機 (的埠，也就是對中央管理存放區) 副本的本機伺服器進行複製。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="1eb0b-112">中央管理存放區的本機複本位於每一部電腦上的 SQL Server 中的 **RTCLOCAL** 資料庫。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="1eb0b-113">複製是從中央管理伺服器 (，或是將中央管理伺服器角色) 至 Edge server 的前端伺服器或前端集區，也是一個內部介面埠。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="1eb0b-114">**下一個躍點選取範圍**</span><span class="sxs-lookup"><span data-stu-id="1eb0b-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="1eb0b-115">從清單中選取 [下一個躍點集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="1eb0b-116">您可以定義 Director、Director 集區、前端伺服器或前端集區，以承擔此角色。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="1eb0b-117">下一個躍點集區是伺服器或伺服器集區，可接受來自 Edge Server 或 Edge 集區內部介面的輸入 SIP 訊息，並將輸出 SIP 傳送至 Edge internal interface。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb0b-118">Director 是選用的角色，如果您決定不部署 Director，則 (單一電腦或集區) 的前端伺服器會承擔 Director 角色。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="1eb0b-119">**外部設定**</span><span class="sxs-lookup"><span data-stu-id="1eb0b-119">**External settings**</span></span>
  
<span data-ttu-id="1eb0b-120">您可以在此區段的屬性中編輯 Edge Server 或 Edge 集區的外部設定屬性。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="1eb0b-121">您可以編輯下列內容：</span><span class="sxs-lookup"><span data-stu-id="1eb0b-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="1eb0b-122">如果您想要將獨特的 IP 位址和完整功能變數名稱指派給每個 Edge Server 服務，請選取 [ **為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1eb0b-123">如果選擇不選取核取方塊，則必須為每個 Edge Service 使用不同的連接埠。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="1eb0b-124">每個 Edge service 會共用針對 Access Edge service 定義的 FQDN，因此會使用相同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="1eb0b-125">每個 Edge 服務必須由不同的 IP 位址搭配相同的連接埠，或相同的 IP 位址搭配唯一的連接埠值唯一識別。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="1eb0b-126">如果您想要將 A/V Edge service 設定為使用專用位址或其他在網路位址轉譯 (NAT) 裝置後隱藏的其他位址，請選取 [ **A/V Edge service 為 NAT** ]。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="1eb0b-127">若要編輯 **Access edge service**，請定義 access edge Service 的 **集區 FQDN** （如 DNS 中所定義的主機 (A）和 AAAA （如果) 記錄和埠值使用 IPv6）</span><span class="sxs-lookup"><span data-stu-id="1eb0b-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="1eb0b-128">若要編輯 **Web 會議 edge service**，請定義 Web 會議 edge Service 的 **集區 FQDN** （如 DNS 中所定義的主機 (a）和 AAAA （如果) 記錄及埠值使用 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="1eb0b-129">若要編輯 **A/V Edge service**，請依主機 (A 定義 A/V Edge Service 的 **集區 FQDN** ，以及在) 記錄及埠值時使用 IPv6 時 AAAA。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1eb0b-130">如果您已選取 [ **為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址** ] 核取方塊，則只有 Access Edge service 集區 FQDN 可供編輯。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="1eb0b-131">請為這三個 Edge Service 各自指派不同的連接埠。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="1eb0b-132">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="1eb0b-133">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="1eb0b-134">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="1eb0b-134">**Help** Displays this help screen.</span></span>
  

