---
title: 避免伺服器維護的新連線至 Lync Server
description: 避免伺服器維護的新連線至 Lync Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd676467cdd6b5bb430f972e48c2f3a53f3f6f14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579829"
---
# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>避免伺服器維護的新連線至 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 可讓您讓伺服器離線 (例如，將軟體或硬體升級) 套用至不會對使用者造成任何服務。

當您指定該選項以防止對集區中的伺服器進行新的連線或呼叫時，該選項會在您正式實作這個選項時停止接受任何新的連線與呼叫。這些新的連線和呼叫會路由轉送給集區中的其他伺服器。伺服器會防止新的連線進入，以讓現有連線的工作階段持續進行到自然結束為止。當所有現有的工作階段都結束時，伺服器就可以準備離線。

當您禁止新的前端伺服器連線時，某些 Lync Server 功能和服務會依賴 DNS 負載平衡，以確保其運作正常。 如果您的集區沒有使用 DNS 負載平衡，透過這些服務進行的連線可能無法在伺服器阻止新的連線傳入期間，由系統重新路由傳送至其他伺服器，因此當該伺服器離線時，有些工作階段及呼叫便會中斷。 以下是仰賴 DNS 負載平衡以確保此選項正常運作的相關功能：

  - 語音應答

  - Conferencing Announcement application

  - 回應群組應用程式

  - 宣告應用程式

  - Call Park application

如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。

除了防止執行 Lync Server 之伺服器上的所有服務的新連線，您也可以防止個別 Lync Server 服務的新連線。 例如，在您需要套用 Lync Server 更新（不需要整個伺服器關閉）的情況下，此方法很有用。 請注意，當您要防止某個服務進行連線，必須選取已經顯示在 Windows 服務清單中的分組服務項目。 例如，Lync Server Front-End 服務和用於監控的資料收集代理程式是不同的 Lync Server 服務，但是在 Windows 服務清單中，他們會進行合併，並顯示為 Lync Server 前端服務。 您可以防止 Lync Server 前端服務的新連線，但您無法單獨阻止這兩個個別基礎 Lync Server 服務的新連線。

<div>


> [!IMPORTANT]
> 設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>若要防止新連接至 Lync Server：

1.  以 Administrators 群組成員的身分登入本機電腦。

2.  開啟 [服務] 嵌入式管理單元主控台：按一下 [ **開始**]，指向 [ **所有程式**]，指向 [系統 **管理工具**]，然後按一下 [ **服務**]。

3.  在清單中，按兩下您要防止新連線的 Lync Server Windows 服務。

4.  在 [內容] 對話方塊的 **[服務狀態: 已啟動]** 下方，按一下 **[暫停]**。

5.  (選用，但建議) 按一下 **[啟動類型]** 旁的 **[手動]**。
    
    <div>
    

    > [!IMPORTANT]
    > 設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。

    
    </div>

6.  完成時，請按一下 **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

