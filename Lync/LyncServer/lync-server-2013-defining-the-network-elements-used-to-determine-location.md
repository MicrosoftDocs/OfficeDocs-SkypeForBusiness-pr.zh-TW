---
title: Lync Server 2013： 定義用於判斷位置的網路元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcd8b78d73ee5f15f893466183f36b2f2ecef32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>定義用來判斷在 Lync Server 2013 中的位置的網路元素

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

如果您正在設定您的 Lync Server 基礎結構，以支援自動用戶端位置偵測，您必須先決定哪些網路即將要用於將來電者對應至位置的項目。 在 Lync Server 2013 中，您可以在下列的第 2 層和第 3 層網路元素關聯位置：

  - 無線存取點 (WAP) 基本服務組識別碼 (BSSID) 位址 (第 2 層)

  - LLDP 交換器連接埠 (第 2 層)

  - LLDP 交換器底座識別碼 (第 2 層)

  - IP 子網路 (第 3 層)

  - 用戶端 MAC 位址 (第 2 層)

網路元素會依照優先順序列出。 如果用戶端可以藉由使用多個網路元素找到，Lync Server 會使用的優先順序，決定要使用哪一個機制。

下列各節會詳細說明每個網路元素的使用方式。

<div>


> [!IMPORTANT]  
> 當您使用網路元素，將來電者對應至位置時，它是責您保留位置資訊服務資料庫最新狀態。 例如，如果您新增或變更網路元素 (如新增 WAP)，則必須在位置資料庫中刪除舊項目並增加新項目。



</div>

<div>

## <a name="wireless-access-point"></a>無線存取點

當用戶端連線至無線網路時，「位置要求」會使用 WAP 的 BSSID 位址來判斷位置。 如果用戶端使用漫遊，所指出的 WAP 可能不是最接近的 WAP，甚至有可能會挑出在建築物中其他樓層的 WAP。 若要指出位置是相近的，可在前面以 Near 或 Close to 描述項加上位置值。

此位置方法會假定每個 WAP 的 BSSID 為靜態。 但是，如果您的 WAP 廠商使用動態指派的 BSSID，從 WAP 取得的 BSSID 可能會產生變更 (可能發生在 WAP 設定變更之後)，無線用戶端在無法接收位置的情況之下可能會離開。 若要避免這種可能性，您需要的每個 WAP 所使用的所有可能 BSSID 位址 Erl 位置資訊服務資料庫中填入。

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP 連接埠和交換器

支援 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 之受管理的乙太網路交換器，可將其識別碼及連接埠資訊公告至相容於 LLDP-MED 的用戶端，您可依位置資料庫查詢用戶端以提供裝置的位置。您可以僅在交換器底座辨識碼上建立 ERL 的關聯，或者可將其對應至連接埠層級。

<div>


> [!NOTE]  
> Lync Server 2013 支援使用 LLDP-MED 決定只有 Lync Phone Edition 裝置和 Windows 8 上執行的 Lync 2013 的位置。 如果您需要使用參數層級來決定的其他位置的第 2 層資料有線 PC 型 Lync 用戶端，您需要使用的用戶端 MAC 位址方法。



</div>

</div>

<div>

## <a name="subnet"></a>子網路

第 3 層 IP 子網路會提供可以用來自動偵測用戶端位置的所有 Lync Server 用戶端所支援的機制。 使用 IP 子網路是設定與管理有線用戶端之最容易的方法。 決定使用子網路前，請先詢問自己下列問題來判斷子網路的位置是否明確到足以正確定位用戶端：

  - 一個或多個用戶端子網路是否涵蓋多個樓層？

  - 一個或多個子網路是否涵蓋多棟建築？

  - 每個用戶端子網路涵蓋多少樓層空間？

如果子網路涵蓋的區域太廣，您可能必須使用其他機制尋找用戶端。但是，以實際應用而言，建議您重新組織其 IP 子網路連線以符合 ERL 位置的精確性需求，才不會提高協力廠商 SNMP 解決方案的成本和複雜性。

</div>

<div>

## <a name="client-mac-address"></a>用戶端 MAC 位址

若要使用用戶端電腦的 MAC 位址尋找來電者，您需要受管理的乙太網路交換器，而且必須部署可探索連線至 (或通過) 這些交換器之 Lync 用戶端 MAC 位址的協力廠商 SNMP 解決方案。 SNMP 解決方案會持續輪詢受管理交換器以取得連線至每個連接埠之端點 MAC 位址目前的對應，以及取得對應的連接埠識別碼。 期間的 Lync 用戶端的位置資訊服務要求，將位置資訊服務所使用的用戶端 MAC 位址，查詢的協力廠商應用程式，並則會傳回任何相符的參數 IP 位址及連接埠識別碼。 位置資訊服務使用此資訊來查詢比對記錄其已發佈層級 2 接線圖，並傳回給用戶端的位置。 如果您使用此選項，請確認 SNMP 應用程式以及已發行的位置資料庫記錄之間的交換器連接埠識別項是一致的。

<div>


> [!NOTE]  
> 部分協力廠商 SNMP 解決方案可支援未受管理的存取交換器；如果為 Lync 用戶端提供服務的交換器未受管理，但受管理的發佈交換器具有上行連結，該受管理之交換器可將連線至存取交換器的 MAC 位址回報至 SNMP 應用程式。 這項資訊會啟用位置資訊服務，來識別使用者的位置。 不過，可能只會將單一 ERL 指派至未受管理之交換器上的所有連接埠，所以只有在存取交換器的底座層級才能取得明確的位置，而非連接埠層級。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

