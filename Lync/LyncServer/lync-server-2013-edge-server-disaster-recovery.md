---
title: Lync Server 2013： Edge Server 嚴重損壞修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad1ac0197c4f7755b334624e46f7cec096897f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528820"
---
# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 中的 Edge Server 災難性修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-12_

如同其他伺服器角色，為 Edge Server 提供高可用性的最佳作法，是在每個網站的集區中部署多部 Edge Server。如果其中一部 Edge Server 中斷連線，集區中的其他伺服器將會繼續提供 Edge Service。

若要啟用嚴重損壞修復程序，您必須將在不同的網站上部署個別 Edge Server 集區。您不需要像是對前端集區一樣，明確將 Edge 集區配對在一起，但是具有多個 Edge 集區仍可在一整個 Edge 集區中斷連線時，提供可用的集區繼續執行作業。下列各節提供各種 Edge Server 功能之嚴重損壞修復的詳細資訊。

<div>

## <a name="remote-access"></a>遠端存取

如果您有多個網站，每個網站都有一部 Edge server 集區，而一個整個 Edge 集區失敗，遠端存取服務將繼續運作，而不需要系統管理員的動作。 在不同的網站建立 Edge 集區時，您不能使用相同的 FQDN。 每個 Edge 集區的 Fqdn 都必須是唯一的 Fqdn (internal 和 external) 。 Edge 集區不使用反向 proxy 發行規則來與前端伺服器交談。 當用戶端重新查詢遠端存取 DNS 服務記錄，且遠端使用者路由傳送至其他網站中的 Edge server 時，就會發生自動容錯移轉。 用戶端會根據 DNS SRV 記錄的優先順序，嘗試每個外部 Edge FQDN。

<div>


> [!NOTE]  
> 若要讓容錯移轉順利運作，請確定防火牆允許從每個集區的前端伺服器與所有 Edge server 通訊。



</div>

</div>

<div>

## <a name="federation"></a>同盟

與其他執行 Lync Server 之組織的同盟關係，輸入的同盟要求會持續運作，只要您有像是異地 DNS 伺服器的解決方案。 務必要瞭解，同盟容錯移轉不會在 SRV 記錄中提供優先順序的容錯移轉。 先前提供的解決方案可協助您提供輸入同盟的嚴重損壞修復功能。

輸出同盟一律透過組織中一部已發行的 Edge 集區或 Edge Server 來設定。 如果此 Edge 集區中斷連線，則必須使用拓撲產生器，變更輸出同盟路由以使用仍在執行的 Edge 集區。 如需詳細資訊，請參閱[在 lync server 2013 中容錯移轉用於 Lync server 同盟的 Edge 集](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)區

</div>

<div>

## <a name="xmpp-federation"></a>XMPP 同盟

以 XMPP 同盟來說，當指定為 XMPP 同盟閘道的 Edge 集區中斷連線時，輸出及輸入流量都會失敗。 若要讓 XMPP 同盟恢復運作，您必須變更 XMPP 同盟以使用其他 Edge 集區。 如需詳細資訊，請參閱 [容錯移轉在 Lync Server 2013 中用於 XMPP 同盟的 Edge 集](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)區。

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Edge 集區失敗但前端集區仍在執行中

如果某個網站上的 Edge 集區失敗，但是該網站上的前端集區仍在執行中，您必須在第一個 Edge 集區中斷連線時，變更前端集區使用其他網站上不同的 Edge 集區。 如需詳細資訊，請參閱 [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。

</div>

</div>

<span> </span>

</div>

</div>

</div>

