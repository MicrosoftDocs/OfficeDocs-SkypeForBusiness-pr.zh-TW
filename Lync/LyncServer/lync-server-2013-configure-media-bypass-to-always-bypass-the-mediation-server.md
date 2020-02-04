---
title: Lync Server 2013：將 [旁路媒體] 設定為 [總是略過轉送伺服器]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0023fba32b24243dc4bf2a12659700ace6dea91a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>在 Lync Server 2013 中設定媒體旁路，以永遠略過中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

<div>


> [!NOTE]  
> 本主題假設您已針對特定的網路電話服務提供者（ITSP），為對等（公開交換電話網絡（PSTN）閘道、IP PBX 或會話邊界控制器（）上的任何干線連線設定媒體旁路您想要媒體略過中繼伺服器的網站或服務。<BR>您不能將媒體設定為永遠略過中繼伺服器，同時也能啟用 [呼叫許可控制]。 這些設定不相容，因此在 Lync Server [控制台] 使用者介面中則是相互排斥的設定。



</div>

除了啟用與對轉送伺服器相關聯的個別幹線連線的媒體旁路，您也必須設定媒體旁路的全域設定。 如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在 Lync 端點與您在中繼連線中設定媒體旁路的任何對等都有良好的連線性。

如果您在 Lync 伺服器端點與所有對等的伺服器端點之間沒有良好的連線，則您必須設定全域媒體旁路設定，才能在下列情況下使用網站和區域資訊採用媒體旁路。 這可讓您在判斷媒體繞過中繼伺服器的時間進行更多控制。 若要這樣做，請使用 [在[Lync server 2013 中設定媒體旁路全域設定] 中的步驟，以使用網站和區域資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)，並[在 lync Server 2013 中將子網與網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>若要讓媒體不使用全域方式，就能一直略過中繼伺服器

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按兩下清單中的**全域**配置。

4.  在 [**編輯全域設定**] 頁面上，選取 [**啟用旁路媒體**] 核取方塊。

5.  按一下 [**永遠略過**]。

6.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 中的媒體旁路和中繼伺服器](lync-server-2013-media-bypass-and-mediation-server.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

