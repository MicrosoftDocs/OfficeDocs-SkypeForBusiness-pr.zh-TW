---
title: Lync Server 2013 電話撥入式會議需求
description: Lync Server 2013 電話撥入式會議需求。
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
ms.openlocfilehash: 0850204993935998c4c098bc7c2866a8a6f3fa1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552479"
---
# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

開始 Lync Server 2013 部署程式之前，您需要規劃下列各項：

  - 連接到公用交換電話網路 (PSTN) 所用的設定

  - 將電話撥入式會議地區指派給撥入存取號碼的策略

  - 您建立會議目錄的策略

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>規劃撥入 PSTN 連接

電話撥入式會議至少需要一個轉送伺服器和至少一個 PSTN 閘道。

您可以在中央網站或分支網站中部署轉送伺服器。 在中央網站中，您可以組合前端集區或 Standard Edition server 上的轉送伺服器，也可以將它部署在獨立的伺服器或集區上。 在分支網站中，您可以在獨立伺服器或 Survivable Branch 裝置的元件上部署轉送伺服器。

您可以在中央網站或分支網站中部署 PSTN 閘道。 在分支網站中，PSTN 閘道可以是獨立或 Survivable 分支裝置的元件。

<div>


> [!NOTE]  
> 電話撥入式會議不會使用媒體旁路，因為 A/V 會議伺服器不支援媒體旁路。



</div>

如需規劃撥入式會議的轉送伺服器和 PSTN 閘道設定的詳細資訊，請參閱規劃檔中的 Lync Server 2013 中的「中繼」 [伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md) 。

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>規劃電話撥入式會議區域

在撥入設定期間，您可以建立撥號對應表和電話撥入式會議存取號碼。 撥號對應表是一組正規化規則，可指定電話號碼中的位數和模式，並將電話號碼轉譯為標準的 e.164 格式，以供通話路由使用。 電話撥入式會議存取號碼是參與者加入會議所撥打的號碼。

每個電話撥入式會議存取號碼都必須與至少一個撥號對應表相關聯。 電話撥入式會議區域會將電話撥入式會議存取號碼與其撥號對應表產生關聯。 當您設定撥號對應表時，您可以指定套用至撥號對應表的電話撥入式會議區域。 當您建立撥入存取號碼時，請選取相關聯的撥號對應表的存取號碼相關聯的地區。

當您建立撥號對應表時，您可以指定撥號對應表的範圍：「使用者範圍」、「集區」範圍或「網站範圍」。 每個使用者都會從套用至使用者的最窄範圍指派撥號對應表。 例如，如果有適用的使用者層級撥號對應表，則會指派給該使用者。 若未套用使用者層級撥號對應表，則會為使用者指派集區層級撥號對應表。 若未套用集區層級撥號對應表，則會為該使用者指派網站層級撥號對應表。 若未套用網站層級撥號對應表，則會將全域撥號對應表指派給使用者。

在您設定撥號對應表之前，請務必規劃您想要命名及使用區域的方式。 下列考慮適用于電話撥入式會議地區：

  - 地區通常是與辦公室或辦事處群組相關聯的地理區域。

  - 語言與撥入存取號碼相關聯。 如果您支援具有多種語言的地理區域，您應該決定要如何定義區域以支援多種語言。 例如，您可以根據地理及語言的組合來定義多個地區，也可以根據地理位置定義單一區域，並為每一種語言使用不同的撥入存取號碼。

  - 當使用者排程會議時，會議預設會使用該使用者的撥號對應表所指定的地區。

  - 預設會在會議邀請中包含區域的所有撥入存取號碼。

  - 請務必將地區命名為區域，使其清晰辨識。 使用者可以使用地區名稱來變更會議的區域，以邀請中包含不同的存取號碼。  (當使用者使用 Outlook 排程會議時，使用者會使用 Lync 2013 的線上會議增益集，以變更地區) 。

  - 應該設計區域，以便任何想要撥入會議的被邀請者，都可以在會議邀請中看到本機存取號碼。

  - 您可以設定地區內的存取號碼顯示在 [電話撥入式會議設定] 頁面 (，也就是使用 Lync Server 管理命令介面 Cmdlet 在會議邀請) 中顯示的順序。

  - 任何位置的任何使用者都可以撥打任何撥入存取號碼，以加入會議。

</div>

<div>

## <a name="planning-for-conference-directories"></a>規劃會議目錄

會議目錄會維護在使用 Lync 2013 時，參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。 會議識別碼的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。 在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。 使用此指導方針時，會議 IDs 通常可以保持很小。 不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼號碼就會成長以支援其他會議。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的轉送伺服器元件](lync-server-2013-mediation-server-component.md)  
[Lync Server 2013 的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

