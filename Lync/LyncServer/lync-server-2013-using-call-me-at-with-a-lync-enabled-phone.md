---
title: Lync Server 2013： 使用呼叫我在與已啟用 Lync 的電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94820ea7f72b0a2a7afc60b6736c02d96695ea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>呼叫我在使用已啟用 Lync 的電話與 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-08-09_

Lync 的呼叫我在功能可讓使用者透過行動電話、 「 園地行 」 或其他裝置已連線至公用交換電話網路 (PSTN) 加入會議的音訊部分。 當您嘗試使用 Lync 加入會議時，您通常會出現與 [**加入會議音訊**] 對話方塊：

![使用 Lync 加入會議音訊] 視窗的螢幕擷取畫面](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入會議音訊] 視窗的螢幕擷取畫面")

如果您選取 [**打電話給我**]，您可以然後選擇下拉式清單中的電話號碼。 Lync Server 2013 將撥打的電話所選取的號碼，以及您可以再使用該電話來參與會議的音訊部分。

在下拉式清單會填入您在 [ **Lync-選項**] 對話方塊的 [**電話**] 索引標籤輸入電話號碼 （例如手機、 住家電話或其他電話）：

![Lync 電話設定選項的螢幕擷取畫面](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 電話設定選項的螢幕擷取畫面")

如果您沒有在 [**電話**] 索引標籤上輸入任何電話號碼然後您必須提供的任何數字] 下拉式方塊中。 不過，您可以一律按一下**新的數字**，並有 Lync Server 撥出您想任何電話號碼：

![Lync 加入會議音訊撥打本人視窗的螢幕擷取畫面](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入會議音訊撥打本人視窗的螢幕擷取畫面")

呼叫我在功能的運作非常好提供其使用其預定的方式： 察覺 Lync Server 通話 PSTN 電話號碼。 不過，您可以執行較不超過最佳的體驗到如果您要求在 Lync 啟用的結束點 （例如，在會議室電話） 呼叫您的 Lync Server。 以下是您可能會遇到，以及兩種方式可解決問題的問題。

若要開始，以下是電話的當呼叫我在功能提供 Lync 啟用的電話號碼時，會發生什麼事。 假設 Ken Myer 會嘗試藉由呼叫他處 1-206-555-1219，已啟用 Lync Server 的電話號碼的 Lync Server 加入會議。 Ken 最初會連線至會議，但之後幾秒鐘 Lync 會顯示訊息，**呼叫未完成，或已經結束**，並 Ken 會顯示已斷線從會議：

![Lync 的螢幕擷取畫面呼叫會議視窗](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 的螢幕擷取畫面呼叫會議視窗")

不過，請注意，已在 Lync 交談視窗內不一致的情形。 Ken Myer 已列於 [**參與者**] 標題下方的唯一名稱。 不過，如果您看] 視窗的標題列中，您會看到會議包含 4 參與者總數。

同樣地，如果您在任何其他會議參與者的 [交談] 視窗中查詢您將不會看到 Ken Myer 列出無所不在：

![Lync 參與者清單視窗螢幕擷取畫面](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 參與者清單視窗螢幕擷取畫面")

尚未，在此同時，Ken myer 的使用者將能夠使用其 Lync 啟用的電話參與通話的音訊部分。 呼叫我在功能實際上具有正常運作，但小於最佳使用者經驗。

有，至少有兩種方式可解決這個問題。 如果您已經有這種方式 （例如 Ken Myer 並未） 加入會議，您通常可以從事不同的形式來解決問題。 例如，如果您要傳送立即訊息 [交談] 視窗會現在會顯示所有會議參與者，包括您自己：

![Lync 交談和參與者清單的螢幕擷取畫面](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 交談和參與者清單的螢幕擷取畫面")

此時您應該能夠參與會議預期的方式。

或者，您可以藉由變更加入會議的方式完全避免此問題。 如果您需要呼叫已啟用 Lync Server 的電話的 Lync Server，您應該稍後加入會議而不需音訊連線。 若要這麼做，請選取 [不加入音訊時出現 [加入會議音訊] 對話方塊：

![Lync 不要加入會議音訊] 視窗的螢幕擷取畫面](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不要加入會議音訊] 視窗的螢幕擷取畫面")

您已經成功連線至會議之後，您可以現在 「 邀請 」 來加入會議也已啟用 Lync Server 的電話。 若要這麼做，將滑鼠放在 [人員] 圖示，然後按一下 [**邀請其他人**：

![Lync 邀請詳細參與者視窗螢幕擷取畫面](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀請詳細參與者視窗螢幕擷取畫面")

將會帶出 [**傳送 IM** ] 對話方塊。 略過對話方塊的標題 （您實際上並不正在傳送立即訊息），並輸入 Lync 啟用的電話的電話號碼：

![傳送 IM] 對話方塊方塊螢幕擷取畫面](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "傳送 IM] 對話方塊方塊螢幕擷取畫面")

按一下 [**確定]** 後，Lync 伺服器就會呼叫在對話方塊中輸入的數字。 連線時，您必須透過 Lync 啟用的電話，完整音訊功能，您將能夠看到並與其互動完整的會議名冊。

</div>

<span> </span>

</div>

</div>

</div>

