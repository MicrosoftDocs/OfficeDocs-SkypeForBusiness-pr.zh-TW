---
title: Edge Server FQDN 設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要在 [外部設定] 底下定義屬性，請設定下列專案：
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684756"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="a164f-103">Edge Server FQDN 設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="a164f-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="a164f-104">若要在 [**外部設定**] 底下定義屬性，請設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="a164f-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="a164f-105">如果您想要為 web 會議和音訊/視頻定義不同的池 FQDN 和 IP 位址，請選取 [**針對 web 會議與 A/V 啟用個別的 FQDN 和 ip 位址**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a164f-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a164f-106">如果您選擇不選取個別 FQDN 和 IP 位址的核取方塊，您必須針對 Edge 伺服器所提供的三種服務分別提供不同的埠。</span><span class="sxs-lookup"><span data-stu-id="a164f-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="a164f-107">唯一要設定的完整功能變數名稱是與存取邊緣服務相關聯的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a164f-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="a164f-108">如果您希望 A/V 邊緣服務使用網路位址轉譯（NAT） IP 位址和設定，請選取 [ **a/v edge 服務已啟用 NAT** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a164f-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="a164f-109">針對已啟用的邊緣服務，您可以在 [**埠**] 底下輸入 [**池 FQDN** ] 和 [埠]</span><span class="sxs-lookup"><span data-stu-id="a164f-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="a164f-110">定義**存取邊緣服務**池 FQDN，以及唯一識別該服務的埠。</span><span class="sxs-lookup"><span data-stu-id="a164f-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="a164f-111">定義**網路會議 Edge 服務**池 FQDN （如果未選取 [web 會議] 和 [a/V] 的不同 FQDN 和 IP 位址）以及唯一識別該服務的埠。</span><span class="sxs-lookup"><span data-stu-id="a164f-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="a164f-112">定義**A/V Edge 服務**池 FQDN （如果未選取 [web 會議] 和 [a/v] 的不同 FQDN 和 IP 位址）以及唯一識別該服務的埠。</span><span class="sxs-lookup"><span data-stu-id="a164f-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="a164f-113">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="a164f-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="a164f-114">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="a164f-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="a164f-115">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="a164f-115">**Help** Displays this help screen.</span></span>
  

