---
title: Lync Server 2013 電話撥入式會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dcdf30ac0fc35f470e74991b2127cd81b05c5c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

在您開始使用 Lync Server 2013 部署程序之前必須規劃的下列：

  - 要用於連線至公用交換的電話網路 (PSTN) 的組態

  - 策略指派給撥入的電話撥入式會議地區的存取號碼

  - 建立會議目錄的策略

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>規劃電話撥入式 PSTN 連線

電話撥入式會議需要至少一部中繼伺服器和至少一個 PSTN 閘道。

您可以部署中繼伺服器在中央網站，或在分支網站中。 在管理中心網站中，您可以組合的中繼伺服器上的前端集區或 Standard Edition 伺服器，或您可以將它部署在獨立伺服器或集區。 在分支網站中，您可以部署中繼伺服器上獨立伺服器，或為 Survivable Branch Appliance 的元件。

您可以部署在中央網站，或在分支網站中的 PSTN 閘道。 在分支網站中，PSTN 閘道可以是獨立或 a Survivable Branch Appliance 的元件。

<div>


> [!NOTE]  
> 電話撥入式會議不使用媒體旁路，因為 A / V 會議伺服器不支援媒體旁路。



</div>

如需規劃您的設定，針對 [中繼伺服器和 PSTN 閘道的撥入式會議的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的中繼伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>規劃撥入式會議區域

電話撥入式組態中，在您建立撥號對應表和電話撥入式會議存取號碼。 撥號對應表是指定的數目和模式的數字的電話號碼，並將電話號碼轉譯成標準 E.164 格式進行通話路由傳送的正規化規則的集合。 電話撥入式會議存取號碼是數字參與者電話加入會議。

每個撥入式會議存取號碼必須是至少一個撥號對應表相關聯。 電話撥入式會議地區關聯其撥號對應表撥入式會議存取號碼。 當您設定撥號對應表時，您會指定套用至撥號對應表撥入式會議區域。 當您建立的撥入存取號碼時，您會選取適當的撥號對應表建立關聯的存取號碼的地區。

當您建立撥號對應表時，您指定的撥號對應表範圍： 使用者範圍、 集區的範圍或網站範圍。 每位使用者是從最窄範圍套用至使用者指派撥號對應表。 例如，使用者如果其中一個適用於指派使用者層級撥號對應表。 如果使用者層級撥號對應表不會套用，指派給使用者集區層級撥號對應表。 如果集區層級撥號對應表不會套用，使用者會指派網站層級撥號對應表。 如果網站層級撥號對應表不會套用，使用者會指派全域撥號對應表。

在您設定的撥號對應表計劃之前，是重要的規劃您要的名稱，並使用區域的方式。 下列考量適用於電話撥入式會議區域：

  - 區域通常是與一個或多個辦公室相關聯的地理區域。

  - 撥入存取號碼與語言相關聯。 如果您支援多種語言的地理區域，您應該決定要如何定義以支援多種語言的地區。 例如，您可以定義多個區域根據組合的 geography 及語言]，或者也可能定義單一區域根據地理位置，具有不同撥入存取號碼的每一種語言。

  - 當使用者排程會議時，根據預設，會議會使用該使用者的撥號對應表所指定的區域。

  - 根據預設，區域的撥入存取號碼的所有隨附在會議邀請。

  - 務必名稱區域，使清楚辨識。 使用者可以變更會議的區域，以便在邀請中包含不同的存取號碼使用區域的名稱。 （當使用者使用 Outlook 來排程會議時，使用者使用線上會議增益集 for Lync 2013 變更地區）。

  - 設計區域應，讓任何想要撥入會議的受邀者可以看到本機存取號碼，在會議邀請。

  - 您可以使用 Lync Server 管理命令介面指令程式設定中存取區域內的數字會出現在 [電話撥入式會議設定] 頁面的順序 （和，因此，在會議邀請中的顯示的順序）。

  - 從任何位置的任何使用者可以撥打任何撥入存取號碼來加入會議。

</div>

<div>

## <a name="planning-for-conference-directories"></a>規劃會議目錄

會議目錄維護參與者使用時使用 Lync 2013 加入會議的英數字元的會議 ID 與電話撥入式會議參與者加入會議所使用的僅限數字鍵台的會議 ID 之間的對應。 會議 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄，可確保在建立大量的會議之前會議 Id 會保持簡短。 在一般每位使用者的會議數目與組織中，我們建議您在集區中建立一個的每個 999 使用者的會議目錄。 使用此指導方針會議識別碼可以通常是保持小型。 不過，一旦 （整個集區） 的會議目錄的數目超過 9，會議 ID 號碼將會成長到支援其他會議。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的中繼伺服器元件](lync-server-2013-mediation-server-component.md)  
[撥號對應表和 Lync Server 2013 中的正規化規則](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

