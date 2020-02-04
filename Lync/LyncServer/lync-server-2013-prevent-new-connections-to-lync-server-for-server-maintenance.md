---
title: 防止新連線至 Lync Server 以進行伺服器維護
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
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>防止新連線至 Lync Server 2013 以進行伺服器維護

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 可讓您讓伺服器離線（例如，將軟體或硬體升級套用），而不會對使用者造成任何服務遺失。

當您指定防止新連線或呼叫池中伺服器的選項時，它會在您執行此選項後立即停止進行任何新的連線與通話。 這些新的連線和通話會透過池中的其他伺服器路由。 防止新連線的伺服器可讓其在現有連線中的會話繼續下去，直到它們自然結束為止。 當所有現有的會話都已結束時，伺服器即可離線使用。

當您禁止與前端伺服器建立新的連線時，某些 Lync Server 功能與服務會依賴 DNS 負載平衡，以確保其正常運作。 如果您不是在該池使用 DNS 負載平衡，在伺服器防範新連線的期間，透過這些服務的連線可能無法重新路由到其他伺服器，因此當伺服器離線時，可能會打斷. 依賴 DNS 負載平衡的功能，以確保此選項正常運作，如下所示：

  - 值守

  - 會議公告應用程式

  - 回應群組應用程式

  - 宣告應用程式

  - 通話駐留應用程式

如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

除了防止執行 Lync Server 的伺服器上所有服務的新連線，您也可以避免個別 Lync Server 服務的新連線。 例如，如果您需要套用不需要整個伺服器即可關閉的 Lync Server 更新，這種方法很有用。 請注意，當您禁止連線某個服務時，您必須選取已群組並顯示在 Windows 服務清單中的服務。 例如，Lync Server 前端服務和用於監視的資料收集代理程式是獨立的 Lync Server services，但在 [Windows 服務] 清單中，它們會進行整合，並顯示為 Lync Server 前端服務。 您可以防止 Lync Server 前端服務的新連線，但您無法單獨避免這兩個個別基礎 Lync 伺服器服務的新連線。

<div>


> [!IMPORTANT]
> 當您將伺服器設定為防止新連線，然後重新開機伺服器時，伺服器會在啟動後立即開始接受新的連線。 若要避免這種情況，請在重新開機伺服器前，將伺服器設定為只暫停並手動繼續。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>若要防止新連線至 Lync Server：

1.  以管理員群組的成員身分登入本機電腦。

2.  開啟 [服務] 管理單元主控台：按一下 [**開始**]，指向 [**所有程式**]，指向 [系統**管理工具**]，然後按一下 [**服務**]。

3.  在清單中，按兩下您要防止新連接的 Lync Server Windows 服務。

4.  在 [內容] 對話方塊中的 [**服務狀態：已啟動**] 底下，按一下 [**暫停**]。

5.  或者，您可以選擇 [**啟動類型**] 旁的 [**手動**]，然後按一下 [建議]。
    
    <div>
    

    > [!IMPORTANT]
    > 當您將伺服器設定為防止新連線，然後重新開機伺服器時，伺服器會在啟動後立即開始接受新的連線。 若要避免這種情況，請在重新開機伺服器前，將伺服器設定為只暫停並手動繼續。

    
    </div>

6.  完成後，請按一下 **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

