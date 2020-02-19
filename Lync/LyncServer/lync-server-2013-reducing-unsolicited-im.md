---
title: Lync Server 2013： 減少來路不明的 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c8aaf86eca6751dbf16ae67d39d0bccd341422e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="30fee-102">Lync Server 2013 的減少來路不明的 IM</span><span class="sxs-lookup"><span data-stu-id="30fee-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30fee-103">_**上次修改主題：** 2013年-12-05_</span><span class="sxs-lookup"><span data-stu-id="30fee-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="30fee-104">智慧型 IM 篩選器應用程式可協助保護您的 Microsoft Lync Server 2013 部署使用最少的使用者經驗降低最常見的病毒。</span><span class="sxs-lookup"><span data-stu-id="30fee-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="30fee-105">智慧型 IM 篩選器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="30fee-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="30fee-106">增強型 URL 篩選</span><span class="sxs-lookup"><span data-stu-id="30fee-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="30fee-107">增強型檔案傳輸篩選</span><span class="sxs-lookup"><span data-stu-id="30fee-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="30fee-p102">使用智慧型 IM 篩選器可以設定篩選器，以封鎖來自企業防火牆外部未知端點之來路不明或潛在有害的立即訊息。 您可以指定用於判斷應封鎖之項目的條件來設定篩選器，例如封鎖內含超連結或具特定副檔名之檔案的即時訊息。</span><span class="sxs-lookup"><span data-stu-id="30fee-p102">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall. You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="30fee-110">部署智慧型 IM 篩選器的應用程式之前，您應先了解如何篩選選項郵件從一個 Lync Server 2013 伺服器路由傳送至另一個時，會套用。</span><span class="sxs-lookup"><span data-stu-id="30fee-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="30fee-111">無論伺服器位於單一組織內，或是涵蓋多個組織界限，套用這些篩選選項的方式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="30fee-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="30fee-112">這種一致性適用於自訂通知和警告文字插入訊息及跨伺服器傳送的方式。</span><span class="sxs-lookup"><span data-stu-id="30fee-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="30fee-p104">建議的篩選選項是允許含有超連結的立即訊息，但要求智慧型 IM 篩選器在該連結前面插入底線來停用連結。如果選擇這個選項，您還可以另外撰寫要在每條含有超連結之立即訊息開頭出現的使用者通知。</span><span class="sxs-lookup"><span data-stu-id="30fee-p104">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it. If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="30fee-p105">第二個篩選選項可允許含有未修改超連結的立即訊息。如果您選擇這個選項，則可以另外撰寫 (建議使用) 會插入在每一條訊息中的使用者警告。</span><span class="sxs-lookup"><span data-stu-id="30fee-p105">A second filtering option is to allow instant messages with unmodified hyperlinks. If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="30fee-p106">第三個選項可封鎖所有包含超連結的立即訊息。如果您選擇這個選項，伺服器就會傳送警告給使用者。您必須撰寫這個警告。</span><span class="sxs-lookup"><span data-stu-id="30fee-p106">A third option is to block all instant messages that contain hyperlinks. If you choose this option, the server sends a warning to the user. You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

