---
title: 防止新連線至 Lync Server 進行伺服器維護
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
ms.openlocfilehash: d3678414e45e556eb7092b923fab4b737bfd4842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>防止新連線至 Lync Server 2013 進行伺服器維護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

Lync Server 可讓您將伺服器離線，（例如，若要套用軟體或硬體升級） 沒有任何遺失的服務給使用者。

當您指定該選項以防止對集區中的伺服器進行新的連線或呼叫時，該選項會在您正式實作這個選項時停止接受任何新的連線與呼叫。這些新的連線和呼叫會路由轉送給集區中的其他伺服器。伺服器會防止新的連線進入，以讓現有連線的工作階段持續進行到自然結束為止。當所有現有的工作階段都結束時，伺服器就可以準備離線。

當您防止新連線至前端伺服器時，某些 Lync Server 功能與服務依賴 DNS 負載平衡設為確保能正確地運作。 如果您的集區沒有使用 DNS 負載平衡，透過這些服務進行的連線可能無法在伺服器阻止新的連線傳入期間，由系統重新路由傳送至其他伺服器，因此當該伺服器離線時，有些工作階段及呼叫便會中斷。 以下是仰賴 DNS 負載平衡以確保此選項正常運作的相關功能：

  - 語音應答

  - Conferencing Announcement application

  - 回應群組應用程式

  - 宣告應用程式

  - Call Park application

如需 DNS 負載平衡的詳細資訊，請參閱規劃文件中的[DNS 負載平衡 Lync Server 2013 中](lync-server-2013-dns-load-balancing.md)。

除了防止新連線，執行 Lync Server 的伺服器上的所有服務，您也可以使用於個別的 Lync Server 服務的新連線。 例如，此方法特別有用的情況下，您要套用不需要整個伺服器關機 Lync Server 更新。 請注意，當您要防止某個服務進行連線，必須選取已經顯示在 Windows 服務清單中的分組服務項目。 例如，Lync Server 前端服務和監視的資料集合代理程式是個別的 Lync Server 服務，但 Windows 的 [服務] 清單中，他們會合併並 Lync Server 前端服務如下所示。 您可以防止新連線的 Lync Server 前端服務，但您無法另外避免這兩項個別基礎 Lync Server 服務的新連線。

<div>


> [!IMPORTANT]
> 設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>若要防止新連線至 Lync Server:

1.  系統管理員群組的成員身分登入本機電腦。

2.  開啟 [服務] 嵌入式管理單元主控台： 按一下 [**開始**、 指向 [**所有程式]**、 指向 [**系統管理工具**]，然後按一下 [**服務**]。

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

