---
title: Lync Server 2013：在前端伺服器上部署 IP 位址類型
description: Lync Server 2013：在前端伺服器上部署 IP 位址類型。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d27cbc6ae23af1f15e28b19e1871c0aaf35dde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559789"
---
# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="42d0c-103">在 Lync Server 2013 的前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="42d0c-103">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d0c-104">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="42d0c-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="42d0c-105">使用拓撲產生器，執行下列程式中的步驟，以在前端伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="42d0c-105">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="42d0c-106">若要在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="42d0c-106">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="42d0c-107">在 [ **Enterprise Edition 前端**集區] 底下的集區中，以滑鼠右鍵按一下伺服器，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="42d0c-107">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="42d0c-108"> (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) </span><span class="sxs-lookup"><span data-stu-id="42d0c-108">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="42d0c-p102">在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="42d0c-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="42d0c-111">**前端伺服器集區的 [編輯內容] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="42d0c-111">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="42d0c-112">![前端伺服器 [編輯內容] 對話方塊](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "前端伺服器 [編輯內容] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="42d0c-112">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="42d0c-p103">**使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="42d0c-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="42d0c-115">此為 IP 版本 6 (IPv6) 組態的建議選項。</span><span class="sxs-lookup"><span data-stu-id="42d0c-115">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="42d0c-116">**將服務使用方式限制為選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="42d0c-116">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="42d0c-117">選取此選項指定在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="42d0c-117">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="42d0c-118">如果您選取此選項，則必須輸入 **主要 IP 位址**的值。</span><span class="sxs-lookup"><span data-stu-id="42d0c-118">If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="42d0c-p105">**主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="42d0c-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="42d0c-122">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="42d0c-122">**PSTN IP address**.</span></span> <span data-ttu-id="42d0c-123">安裝額外的網路介面卡 (NIC) s，以支援 Lync Server 2013 的 PSTN IP 位址設定，但不支援組合轉送伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="42d0c-123">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="42d0c-124">如需 Lync Server 2013 支援的 NIC 設定的詳細資訊，請參閱 [伺服器硬體平臺的 Lync server 2013](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="42d0c-124">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

