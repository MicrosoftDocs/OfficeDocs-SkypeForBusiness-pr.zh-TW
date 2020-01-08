---
title: Lync Server 2013：定義用來判斷位置的網元
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>定義用來判斷 Lync Server 2013 中的位置的網路元素

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

如果您設定 Lync Server 基礎結構以支援自動用戶端位置偵測，您必須首先決定要使用哪些網路元素將呼叫者對應至位置。 在 Lync Server 2013 中，您可以將下列第2層和第3層網路元素與位置建立關聯：

  - 無線存取點（WAP）基本服務集標識（BSSID）位址（第2層）

  - LLDP 切換埠（第2層）

  - LLDP 切換主機殼識別碼（第2層）

  - IP 子網（第3層）

  - 用戶端 MAC 位址（第2層）

網路元素會依優先順序順序列出。 如果您使用一個以上的網元來找出用戶端，Lync Server 會使用優先順序順序來決定要使用哪種機制。

下列各節提供使用每個網元的詳細資料。

<div>


> [!IMPORTANT]  
> 當您使用網路元素將呼叫者對應到位置時，將位置資訊服務資料庫保持在最新狀態，這是一項非常重要的重要性。 例如，如果您新增或變更網路元素（例如新增 WAP），則必須刪除舊專案，並在位置資料庫中新增新的專案。



</div>

<div>

## <a name="wireless-access-point"></a>無線存取點

當用戶端以無線方式連線到網路時，位置要求會使用 WAP 的 BSSID 位址來決定其位置。 如果用戶端是漫遊，則所指示的 WAP 可能不是最接近的物件，而且您甚至可以在建築物的不同基底，挑選一個 WAP。 若要指出位置是近似值，您可以在 location 值前面加上接近或接近的描述項。

這個位置方法假設每個 WAP 的 BSSID 都是靜態的。 不過，如果您的 WAP 供應商使用的是動態指派的 BSSIDs，則從 WAP 取得的 BSSID 可能會變更（在 WAP 設定變更之後，可能會發生這種情況），而且無線用戶端可能不會收到位置。 若要防止這種可能性，您必須使用 ERLs，為每個 WAP 所使用的所有可能的 BSSID 位址填入位置資訊服務資料庫。

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP 埠和交換器

支援連結層探索通訊協定的受管理乙太網交換器：媒體端點探索（LLDP-MED-V）可將其身分識別和埠資訊宣告至 LLDP 相容的用戶端，然後可以針對 location 資料庫進行查詢，以提供裝置的位置。 您可以將 ERLs 完全與交換器主機殼識別碼相關聯，或者您可以將它們對應到埠層級。

<div>


> [!NOTE]  
> Lync Server 2013 支援使用 LLDP-MED-V 判斷只有 Lync Phone Edition 裝置和在 Windows 8 上執行 Lync 2013 的位置。 如果您需要使用交換器層級的第2層資料來判斷其他有線電腦的 Lync 用戶端的位置，您必須使用用戶端 MAC 位址方法。



</div>

</div>

<div>

## <a name="subnet"></a>子網路

第3層 IP 子網提供所有 Lync Server 用戶端所支援的機制，可讓您自動偵測用戶端位置。 使用 IP 子網是設定及管理有線用戶端最簡單的位置方法。 不過，在您決定要使用子網之前，請先使用下列問題來協助判斷子網的位置是否正確，才能準確找到用戶端：

  - 一或多個用戶端子網涵蓋多個地面嗎？

  - 一個或多個子網是否涵蓋了多個建築物？

  - 每個用戶端子網上所覆蓋的占地空間是多少？

如果子網覆蓋範圍太寬，您可能需要使用其他機制來尋找用戶端。 不過，如果您有任何實際的情況，我們建議客戶重組其 IP 子網，以符合 ERL 位置的具體需求，而不是產生協力廠商 SNMP 解決方案的成本與複雜性。

</div>

<div>

## <a name="client-mac-address"></a>用戶端 MAC 位址

若要使用用戶端電腦的 MAC 位址來尋找來電者，您需要受管理的乙太網交換器，而且您必須部署協力廠商 SNMP 解決方案，以探索連接至（或透過）這些交換器的 Lync 用戶端 MAC 位址。 SNMP 解決方案會持續輪詢受管理的交換器，以取得連線至每個埠的端點 MAC 位址的目前對應，並取得對應的埠識別碼。 在 Lync 用戶端的位置資訊服務要求期間，位置資訊服務會使用用戶端的 MAC 位址來查詢協力廠商應用程式，然後傳回任何相符的切換 IP 位址與埠識別碼。 位置資訊服務會使用此資訊來針對相符記錄查詢其發佈的 Layer 2 wiremap，並將位置傳回給用戶端。 如果您使用這個選項，請確認 SNMP 應用程式與發佈的位置資料庫記錄之間的切換埠識別碼一致。

<div>


> [!NOTE]  
> 某些協力廠商 SNMP 解決方案可以支援未受管理的存取交換器;如果將服務 Lync 用戶端的開關設為未受管理，但有一個上行鏈路到受管理的發佈交換器，則受管理的交換器可以向 SNMP 應用程式傳回連接至 access 切換的用戶端的 MAC 位址。 此資訊可讓位置資訊服務識別使用者的位置。 不過，您可以只將單一 ERL 指派給非託管交換器上的所有埠，因此只有在存取開關的主機殼層級（而非埠層級）才能使用位置的最高值。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

