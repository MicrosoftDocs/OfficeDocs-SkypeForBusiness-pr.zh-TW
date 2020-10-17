---
title: Lync Server 2013：公用機碼基礎結構
description: Lync Server 2013：公用機碼基礎結構。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b8f2ee8c6b1524cec461ad90a4d4cb1a1003b51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565559"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a>Lync Server 2013 的公用機碼基礎結構

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-13_

Microsoft Lync Server 2013 依賴伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 及 Windows Server 2003 Public Key 基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。

憑證是數位 IDs。 它們會以名稱識別伺服器，並指定其屬性。 為了確保憑證上的資訊有效，憑證必須由用戶端或連接至伺服器的其他伺服器所信任的 CA 所發出。 如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。 如果伺服器與私人網路絡外的實體互動，則可能需要公用 CA。

即使憑證上的資訊有效，仍然必須以某種方式驗證提供憑證的伺服器確實是憑證所代表的伺服器。 這是 Windows PKI 的所在位置。

每一個憑證都會連結到公開金鑰。 憑證上命名的伺服器擁有只有本身知道的對應私密金鑰。 連接的用戶端或伺服器會使用公開金鑰加密資訊的任意片段，並將它傳送至伺服器。 如果伺服器解密資訊並將其傳回為純文字，則連接實體可以確定伺服器是否要將私密金鑰保留在憑證中，因此是憑證中命名的伺服器。

<div>


> [!NOTE]  
> 並非所有公用 Ca 都符合 Lync Server 2013 憑證的需求。 我們建議您參考已驗證的公用 CA 廠商清單，以滿足您的公用憑證需求。 如需詳細資訊，請參閱整合通訊憑證合作夥伴，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> 。



</div>

<div>

## <a name="crl-distribution-points"></a>CRL 發佈點

Lync Server 2013 要求所有伺服器憑證包含一或多個憑證吊銷清單 (CRL) 發佈點。 CRL 發佈點 (Cdp) 是可從中下載 Crl 的位置，目的在於驗證憑證自發行之後起尚未撤銷，且憑證仍在有效期限內。 CRL 發佈點會在憑證的內容中注明為 URL，且通常為安全的 HTTP。

</div>

<div>

## <a name="enhanced-key-usage"></a>增強型金鑰使用方式

由於伺服器驗證的目的，Lync Server 2013 需要所有伺服器憑證以支援增強型金鑰使用 (EKU) 。 設定 [伺服器驗證的 EKU] 欄位表示憑證是有效的，目的在於驗證服務器。 這個 EKU 對 MTLS 而言是必要的。 您可以在 EKU 中有一個以上的專案，為憑證啟用一個以上的目的。

<div>


> [!NOTE]  
> 即時通訊伺服器2003和即時通訊伺服器2005中的輸出 MTLS 連線需要用戶端驗證 EKU，但是不再需要。 不過，此 EKU 必須存在於透過公用 IM 連線方式連線到 AOL 的 Edge Server 上。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

