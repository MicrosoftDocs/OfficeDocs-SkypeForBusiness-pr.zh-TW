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
ms.openlocfilehash: 0c54e162aeda43730dea471732124023588e9041
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

開始進行 Lync Server 2013 部署程式之前，您需要規劃下列各項：

  - 用來連線到公用交換電話網絡（PSTN）的設定

  - 將電話撥入式會議區域指派給撥入式存取號碼的策略

  - 建立會議目錄的策略

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>規劃撥入 PSTN 連接

電話撥入式會議需要至少一個中繼伺服器和至少一個 PSTN 閘道。

您可以在中央網站或分支網站中部署中繼伺服器。 在中央網站中，您可以 collocate 前端池或標準版伺服器上的中繼伺服器，或將它部署在獨立伺服器或池中。 在分支網站中，您可以在獨立伺服器或 Survivable 分支裝置的元件上部署轉送伺服器。

您可以在中央網站或分支網站中部署 PSTN 閘道。 在分支網站中，PSTN 閘道可以獨立或 Survivable 分支裝置的元件。

<div>


> [!NOTE]  
> 電話撥入式會議不會使用媒體旁路，因為 A/V 會議伺服器不支援媒體旁路。



</div>

如需規劃您為進行電話撥入式會議的中繼伺服器和 PSTN 閘道設定的詳細資料，請參閱規劃檔中的[Lync server 2013 中的中繼伺服器元件與拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>規劃電話撥入式會議區域

在撥入設定期間，您會建立撥號方案和電話撥入式會議存取號碼。 撥號方案是一組正常化規則，可指定電話號碼中的數位和位數，並將電話號碼轉譯為呼叫路由的標準 e. 164 格式。 電話撥入式會議存取號碼是參與者加入會議的電話號碼。

每個電話撥入式會議存取號碼必須與至少一個撥號方案相關聯。 電話撥入式會議區域會將電話撥入式會議存取號碼與撥號方案建立關聯。 當您設定撥號方案時，請指定適用于撥號計畫的電話撥入式會議區域。 當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。

當您建立撥號方案時，您可以指定撥號方案的範圍： [使用者範圍]、[池範圍] 或 [網站範圍]。 每個使用者都會從適用于使用者的最窄範圍指派撥號方案。 例如，如果您有一個使用者層級撥號方案，則會指派給該使用者。 如果沒有套用使用者層級撥號方案，則會將使用者指派為「泳池層級撥號」方案。 如果沒有套用池層級撥號方案，就會為使用者指派網站層級的撥號方案。 如果網站層級撥號方案不適用，則會為使用者指派全域撥號方案。

在您設定撥號方案之前，請務必規劃您想要如何命名及使用地區。 下列考慮適用于電話撥入式會議區域：

  - 地區通常是與辦公室或辦公室群組相關聯的地理區域。

  - [語言] 與 [撥入存取號碼] 相關聯。 如果您支援具有多種語言的地理區域，您應該決定要如何定義區域來支援多種語言。 例如，您可能會根據地理與語言的組合來定義多個區域，或者您可以根據地理位置定義單一區域，並針對每個語言使用不同的撥入存取號碼。

  - 當使用者排程會議時，預設情況下，會議會使用該使用者撥號計畫所指定的區域。

  - 根據預設，該區域的所有撥入存取號碼都會包含在會議邀請中。

  - 請務必為區域命名，以便清楚辨識。 使用者可以使用地區名稱來變更會議的區域，以便邀請中包含不同的存取號碼。 （當使用者使用 Outlook 排程會議時，使用者會使用 Lync 2013 的線上會議增益集來變更區域）。

  - 區域應該設計為想要撥入會議的任何被邀請者，都可以在會議邀請中看到本機存取號碼。

  - 您可以在 [電話撥入式會議設定] 頁面（也就是這些號碼在會議邀請中出現的順序），使用 Lync Server 管理命令介面 Cmdlet 來設定其在區域內顯示的順序。

  - 任何位置的使用者都可以呼叫任何撥入存取號碼來加入會議。

</div>

<div>

## <a name="planning-for-conference-directories"></a>規劃會議目錄

在使用 Lync 2013 時，會議目錄會維持參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。 會議 ID 的格式如下所示：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄可確保會議 Id 保持不變，直到建立大量的會議為止。 在每位使用者有典型會議數的組織中，我們建議您為池中的每個999使用者建立一個會議目錄。 使用這種準則，會議 Id 通常可以保持很小的狀態。 不過，一旦會議目錄數（跨多個池）超過9個，會議 ID 號碼就會增長以支援其他會議。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的中繼伺服器元件](lync-server-2013-mediation-server-component.md)  
[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

