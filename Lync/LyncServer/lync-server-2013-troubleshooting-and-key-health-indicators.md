---
title: Lync Server 2013：疑難排解與主要健康情況指示器
description: Lync Server 2013：疑難排解與主要狀況指標。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting and Key Health Indicators
ms:assetid: 14ec9e21-aa2b-4d65-9be4-ef2adfbe9a8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720322(v=OCS.15)
ms:contentKeyID: 63969585
ms.date: 05/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdb214d4ce8472800272a05e81b0402d3bf820e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549049"
---
# <a name="troubleshooting-and-key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="4a150-103">Lync Server 2013 中的疑難排解與重要狀況指示器</span><span class="sxs-lookup"><span data-stu-id="4a150-103">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a150-104">_**主題上次修改日期：** 2015-05-18_</span><span class="sxs-lookup"><span data-stu-id="4a150-104">_**Topic Last Modified:** 2015-05-18_</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4a150-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4a150-105">In This Section</span></span>

<span data-ttu-id="4a150-106">為了符合參考架構 Sla，並確保順利轉接至我們的支援小組，一般的疑難排解方法必須定義在一起，以及 Lync Server [網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677) 中所定義的一組必要疑難排解工具和方法。</span><span class="sxs-lookup"><span data-stu-id="4a150-106">To meet the Reference Architecture SLAs and to ensure a smooth transition to our support teams, a common troubleshooting approach must be defined together with a required set of troubleshooting tools and approaches as defined in the Lync Server [Networking guide](https://go.microsoft.com/fwlink/p/?linkid=390677) .</span></span>

<span data-ttu-id="4a150-107">強烈建議使用 System Center Operations Manager 來監視 Lync Server 2013 系統的健康情況。</span><span class="sxs-lookup"><span data-stu-id="4a150-107">We strongly recommend that System Center Operations Manager be used to monitor the health of the Lync Server 2013 system.</span></span> <span data-ttu-id="4a150-108">此外，請參閱《 Lync Server 2013 [網路指南》](https://go.microsoft.com/fwlink/p/?linkid=390677) 中的 KHIs 討論和 Excel 試算表，以與 lync 2013 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4a150-108">Also, refer to the discussion of KHIs in the Lync Server 2013 [Networking guide](https://go.microsoft.com/fwlink/p/?linkid=390677) and the Excel spreadsheet for use with Lync 2013.</span></span>

</div>

<div>

## <a name="reference"></a><span data-ttu-id="4a150-109">參考</span><span class="sxs-lookup"><span data-stu-id="4a150-109">Reference</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="4a150-110">相關各節</span><span class="sxs-lookup"><span data-stu-id="4a150-110">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

