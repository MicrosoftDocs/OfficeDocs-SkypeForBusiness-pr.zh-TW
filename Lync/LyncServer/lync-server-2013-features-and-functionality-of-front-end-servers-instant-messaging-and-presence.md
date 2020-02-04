---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的功能
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
ms.openlocfilehash: 4a76dfed553e85838739c7c348e5bc53fc9943a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-17_

前端伺服器提供大部分的 Lync 伺服器功能。 有兩個可用的版本： Lync Server Enterprise Edition，主要針對大型組織和 Lync Server Standard Edition 設計，主要針對需要較小硬體 investement 且不需要的較小組織。需要高可用性。 這兩種版本都支援所有 Lync 伺服器的工作負載，包括 IM、目前狀態、會議和企業語音。

[立即訊息（IM）] 可讓您的使用者在電腦上使用文字型郵件即時相互通訊。 支援兩方和多方 IM 會話。 在雙方的 IM 交談中，參與者可以隨時新增協力廠商參與者加入交談。 發生這種情況時，交談視窗會變更以支援會議功能。

<div>


> [!IMPORTANT]
> 當 Lync 與 Communicator 用戶端參與單一通訊時，通常稱為對等。 從技術角度來看，兩個用戶端都是以單一交談的方式進行通訊，中間是中間的立即訊息 multipoint 控制項單位（IMMCU）。 IMMCU 是前端伺服器的元件。 將 IMMCU 放在所需的通訊工作流程中，即可允許通話詳細資料錄製，以及前端伺服器所能啟用的其他功能。 通訊來自用戶端上的動態來源埠到前端伺服器埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性）。 透過設計、對等通訊（以及多方 IM），只有當 Lync Server 與 IMMCU 處於作用中且可用時，才可以使用。



</div>

[*目前狀態] 提供資訊*給使用者，瞭解網路上其他人的狀態。 使用者的目前狀態會提供資訊，協助其他人決定是否應該嘗試與使用者聯繫，以及是否要使用立即訊息、電話或電子郵件。 如果可能的話，目前狀態會鼓勵立即通訊，但它也會提供使用者是否在會議中或不在辦公室的相關資訊，指出無法進行立即通訊。 在 Lync 和其他存在感知的應用程式中，此目前狀態會顯示為「目前狀態」圖示，包括 Microsoft Outlook 訊息與共同作業用戶端、Microsoft SharePoint 技術、Microsoft Word 及 Microsoft Excel 試算表軟體. [目前狀態] 圖示代表使用者目前的可用性和溝通意願。

</div>

<span> </span>

</div>

</div>

</div>

