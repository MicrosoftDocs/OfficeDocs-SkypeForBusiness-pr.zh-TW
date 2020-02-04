---
title: Lync Server 2013 電話撥入式會議概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

如果您的組織擁有的使用者需要在不在辦公室或無法存取電腦的情況下，出席 Lync Server 2013 內部部署會議，則可以部署電話撥入式會議，讓他們可以使用公開的交換電話加入會議網路（PSTN）電話。

電話撥入式會議是您可以在部署 Lync Server 2013 會議時設定的選擇性功能。 雖然電話撥入式會議使用的是企業語音用途的一些相同的 Lync Server 2013 元件，但是您可以部署電話撥入式會議，即使您沒有部署企業語音也一樣。

<div>


> [!NOTE]  
> 如果您要部署電話撥入式會議，您必須在部署 Lync Server 2013 會議的每個池中部署它。 您不需要在每個池中指派存取號碼，但您必須在每個池中部署撥入功能。 當使用者從某個池中呼叫存取號碼以在不同的池中加入 Lync Server 2013 會議時，此需求支援所記錄的名稱功能。



</div>

會議必須在會議原則中啟用撥入存取。 根據預設，啟用撥入存取的會議在會議邀請中包含下列資訊：

  - 識別會議的數位會議 ID。

  - 一或多個 PSTN 存取號碼。

  - [電話撥入式會議設定] 頁面的連結，其中包含其相關語言的完整存取號碼清單;建立、重設或解除封鎖個人身分識別號碼（Pin）的位置;以及其他資訊，例如雙音調多重頻率（DTMF）控制。

電話撥入式會議支援企業和匿名使用者。 企業使用者在其組織內擁有 Active Directory 網域服務認證和 Lync Server 2013 帳戶。 匿名使用者沒有貴組織內的企業認證。 在電話撥入式會議的內容中，聯盟夥伴組織中使用 PSTN 連接至會議的使用者，會被視為匿名使用者。 對於電話撥入式會議，與其他內容不同，聯盟使用者不會經過驗證。

加入已啟用電話撥入存取的會議的企業使用者或會議領導者，請撥打電話給其中一個會議存取號碼，然後系統會提示您輸入會議 ID。 如果領導者尚未加入會議，使用者可以輸入其整合通訊（UC）延伸（或完整的電話號碼），並釘選給領導，或等候接受者承認。 會議召集人只需輸入 PIN，就可以將會議加入為主持人。 前端伺服器使用完整的電話號碼或分機，以及 PIN 的組合，以唯一的方式將企業使用者對應至其 Active Directory 認證。 因此，企業使用者是透過會議中的名稱進行驗證及識別。 企業使用者也可以假設由召集人預先定義的會議角色。

<div>


> [!NOTE]  
> 從 office IP 手機或 Lync Server 2013 或 Lync 2010 應答撥入的企業使用者，不會因已驗證，而提示他們輸入電話號碼。



</div>

想要加入電話撥入式會議的匿名使用者撥打電話給其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。 未經驗證的匿名使用者也會收到記錄其名稱的提示。 所記錄的名稱會識別會議中未經驗證的使用者。 除非至少有一個領導或經過驗證的使用者已加入，且無法指派預先定義的角色，否則匿名使用者將無法獲准參與會議。

<div>


> [!NOTE]  
> 選擇不輸入其電話號碼和 PIN 的企業使用者未經過驗證。 系統會提示他們記錄其名稱，並在會議中被視為匿名使用者。



</div>

在排程時間，會議召集人可以選擇將會議設為關閉或鎖定，以限制會議的存取權。 在這種情況下，系統會要求撥入使用者進行驗證。 如果撥入使用者失敗，或選擇不進行驗證，就會將它們傳輸到大廳。 它們會在大廳等候，直到前置字元接受或拒絕，或者它們結束並中斷連接。 如果電話撥入的使用者正在等待會議，請聆聽音樂。 在他們獲准加入會議之後，撥入使用者可以參與會議的音訊部分，而且可以使用電話鍵台來行使雙音多頻率（DTMF）命令。 [撥入前置字元] 可以行使 DTMF 命令，以將參與者的開啟或關閉、鎖定或解除鎖定，以及開啟或關閉公告的功能。 前置字元也可以使用 DTMF 命令，讓所有人都能透過它來變更會議的許可權，以允許後續加入的任何人。 所有撥入參與者都可以行使 DTMF 命令來聽取說明、聆聽會議名單並將自己設為靜音。

撥入參與者（無論是從 PSTN 撥號），在會議期間聆聽個人宣告（例如是否已靜音或已取消靜音），或是現正播放會議，或是有人正在大廳等候。

<div>


> [!NOTE]  
> 若參與者是透過按一下連結而不是撥號來加入會議，請勿聽到個人公告。



</div>

</div>

<span> </span>

</div>

</div>

</div>

