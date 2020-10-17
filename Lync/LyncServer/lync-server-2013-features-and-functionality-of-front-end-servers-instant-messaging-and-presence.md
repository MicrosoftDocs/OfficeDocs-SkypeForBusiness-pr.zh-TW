---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的特性與功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f80eb823af5ec50c18390fe2ebca2b25498874
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515370"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中前端伺服器、立即訊息及顯示狀態的功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

前端伺服器提供大部分的 Lync Server 功能。 有兩種可供使用的版本： Lync Server Enterprise Edition 主要專為較大的組織和 Lync Server Standard Edition 設計，其主要是針對需要較小硬體 investement 且不需要高可用性的小型組織所設計。 這兩種版本都支援所有的 Lync Server 工作負載，包括 IM、顯示狀態、會議及 Enterprise Voice。

立即訊息 (IM) 可讓使用者在電腦上使用文字訊息，與其他使用者進行即時溝通。同時支援雙方或多方 IM 工作階段。雙方 IM 交談中的參與者可以隨時將第三個參與者加入交談中。若發生這種情況，[交談] 視窗會變更成可支援會議功能。

<div>


> [!IMPORTANT]
> Lync 和 Communicator 用戶端與單一通訊相關時，通常稱為對等。 從技術角度來看，這兩個用戶端是透過單一交談進行通訊，而立即訊息 multipoint control unit (IMMCU) 中間。 IMMCU 是前端伺服器的元件。 在所需的通訊工作流程中放置 IMMCU，可讓您在前端伺服器上啟用詳細通話記錄及其他功能。 通訊來自用戶端的動態來源埠至前端伺服器埠 TLS/TCP/5061 (假設使用建議的傳輸層安全性) 。 根據設計，對等通訊 (，而且只有在 Lync Server 和 IMMCU 為使用中且可用時，才可以進行多方的 IM) 。



</div>

「目前狀態」** 可為使用者提供網路上其他使用者的狀態資訊。 使用者的目前狀態所提供的資訊有助於其他人決定是否應嘗試連絡該名使用者，以及是否要使用立即訊息、電話或電子郵件。 目前狀態會促進立即通訊，但也會提供使用者正在開會中或不在辦公室的資訊，指出無法進行立即通訊。 這種目前狀態會顯示為 Lync 中的目前狀態圖示及其他狀態識別應用程式，包括 Microsoft Outlook 訊息和共同作業用戶端、Microsoft SharePoint 技術、Microsoft Word 和 Microsoft Excel 試算表軟體。 目前狀態圖示表示使用者目前是否有空，以及通訊意願。

</div>

<span> </span>

</div>

</div>

</div>

