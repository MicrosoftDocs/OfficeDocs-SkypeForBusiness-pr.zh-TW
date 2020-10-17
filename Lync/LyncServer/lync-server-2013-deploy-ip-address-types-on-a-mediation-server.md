---
title: Lync Server 2013：在轉送伺服器上部署 IP 位址類型
description: Lync Server 2013：在轉送伺服器上部署 IP 位址類型。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa3be8d1ef12629dc185f98b95d2db0e565cf18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559779"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="86380-103">在 Lync Server 2013 的轉送伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="86380-103">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86380-104">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="86380-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="86380-105">使用拓撲產生器，執行下列程式中的步驟，以在轉送伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="86380-105">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="86380-106">在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="86380-106">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="86380-107">在 [拓撲產生器] 的 [中繼集區 **] 下，** 于集區中的伺服器上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="86380-107">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="86380-108"> (或者，選取伺服器，然後按一下 [**動作**] 功能表中的 [**編輯屬性**]。 ) </span><span class="sxs-lookup"><span data-stu-id="86380-108">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="86380-p102">在 **[編輯內容]** 對話方塊中，選取您想要設定的 IP 位址類型。針對雙重堆疊設定，選取 **[啟用 IPv4]** 和 **[啟用 IPv6]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="86380-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="86380-111">**中繼伺服器集區的編輯內容對話方塊**</span><span class="sxs-lookup"><span data-stu-id="86380-111">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="86380-112">![含 FQDN 的 Lync Server 一般屬性頁面](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "含 FQDN 的 Lync Server 一般屬性頁面")</span><span class="sxs-lookup"><span data-stu-id="86380-112">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="86380-p103">**使用所有設定的 IP 位址**。如果您想要提供使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="86380-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86380-115">此為 IP 版本 6 (IPv6) 組態的建議選項。</span><span class="sxs-lookup"><span data-stu-id="86380-115">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="86380-p104">**將服務使用方式限制為選取的 IP 位址**。選取此選項指定在新伺服器上使用的特定位址。如果您選取此選項，您必須輸入主要 IP 位址的值。</span><span class="sxs-lookup"><span data-stu-id="86380-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="86380-p105">**主要 IP 位址**。輸入伺服器將用於所有通訊 (公用交換電話網路 (PSTN) 除外) 的 IP 位址。輸入的 IP 位址必須符合選取位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="86380-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="86380-122">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="86380-122">**PSTN IP address**.</span></span> <span data-ttu-id="86380-123">當轉送伺服器為獨立時，請定義 PSTN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="86380-123">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="86380-124">此位址必須符合所選位址類型的格式。</span><span class="sxs-lookup"><span data-stu-id="86380-124">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86380-125">安裝額外的網路介面卡 (NIC) s，以支援 Lync Server 2013 的 PSTN IP 位址設定，但不支援組合轉送伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="86380-125">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="86380-126">如需 Lync Server 2013 支援的 NIC 設定的詳細資訊，請參閱 <A href="lync-server-2013-server-hardware-platforms.md">伺服器硬體平臺的 Lync server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="86380-126">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

