---
title: Lync Server 2013：在啟用 Lync 功能的手機上使用 [呼叫我]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>在啟用 Lync 的電話和 Lync Server 2013 上使用 [呼叫我]

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-09_

Lync 中的 [呼叫我] 功能可讓使用者使用手機、「土地線」或連線至公用交換電話網絡（PSTN）的其他裝置，加入會議的音訊部分。 當您嘗試使用 Lync 加入會議時，通常會顯示 [**加入會議音訊**] 對話方塊：

![使用 lync 加入會議音訊視窗螢幕擷取畫面](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 lync 加入會議音訊視窗螢幕擷取畫面")

如果您選取 [**撥打電話給我**]，您就可以從下拉式清單中挑選電話號碼。 Lync Server 2013 會將電話撥打電話給選取的號碼，然後您就可以使用該手機參與會議的音訊部分。

下拉式清單是由您在 [ **Lync –選項**] 對話方塊中的 [**電話**] 索引標籤上輸入的電話號碼（適用于行動電話、家用電話或其他手機）所填入：

![Lync 手機設定選項螢幕擷取畫面](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 手機設定選項螢幕擷取畫面")

如果您沒有在 [**電話**] 索引標籤上輸入任何電話號碼，下拉式方塊中就不會有任何可用的號碼。 不過，您可以隨時按一下 [**新號碼**]，讓 Lync Server 撥號到您想要的任何電話號碼：

![Lync 加入會議按鍵撥號給我視窗螢幕擷取畫面](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入會議音訊撥號我視窗螢幕擷取畫面")

[給我的通話方式] 功能非常符合您的使用方式，因此您可以使用它：讓 Lync Server 呼叫 PSTN 電話號碼。 不過，如果您要求 Lync Server 在啟用 Lync 的端點（例如會議室中的手機）撥打電話給您，您可以執行到最佳的體驗。 以下是您可能遇到的問題，以及解決問題的兩種方法。

若要開始，以下是當您使用支援 Lync 的電話號碼提供電話號碼給我時，會發生的情況。 如果 Ken Myer 嘗試加入會議，請讓 Lync Server 在1-206-555-1219 （即啟用 Lync 伺服器的電話號碼）撥打電話給他。 Ken 最初會連線到會議，但在幾秒之後，Lync 會顯示訊息通話未**完成或已結束**，且 Ken 將會顯示在會議中：

(images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通話會議視窗螢幕")快照 [ ![lync 通話會議] 視窗]的螢幕擷取畫面

但請注意，Lync 交談視窗中有一些差異。 Ken Myer 是 [**參與者**] 標題下所列的唯一名稱。 不過，如果您在視窗的標題列中查看，您會看到會議中總共包含4個參與者。

同樣地，如果您在 [交談] 視窗中查看任何其他會議參與者，您將不會看到在任何位置列出的 Ken Myer：

![Lync 參與者清單視窗螢幕擷取畫面](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "lync 參與者清單視窗螢幕擷取畫面")

而且，Ken Myer 將能使用其 Lync 啟用的手機來參與通話的音訊部分，。 [通話我的功能已實際運作]，但使用者體驗不是最佳的。

您至少有兩種方法可以解決這個問題。 如果您已以這種方式加入會議（例如 Ken Myer），您通常可以使用不同的模態來解決問題。 例如，如果您傳送立即訊息，[交談] 視窗現在會顯示所有會議參與者，包括您自己：

![Lync 交談與參與者清單螢幕擷取畫面](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "lync 交談與參與者清單螢幕擷取畫面")

此時，您應該能夠以預期的方式參與會議。

或者，您可以變更加入會議的方式，完全避免這個問題。 如果您需要讓 Lync Server 呼叫 Lync Server 啟用的手機，您應該先加入沒有音訊連線的會議。 若要這樣做，請選取 [加入會議音訊時不加入音訊] 對話方塊：

![Lync 不加入會議音訊視窗螢幕擷取畫面](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入會議音訊視窗螢幕擷取畫面")

成功連線到會議之後，您現在可以「邀請」 Lync Server 啟用的手機加入會議。 若要這樣做，請將滑鼠放在人員圖示上，然後按一下 [**邀請其他人**]：

![Lync 邀請其他參與者視窗螢幕擷取畫面][(images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "lync 邀請其他參與者] 視窗螢幕")快照

這會顯示 [**傳送 IM** ] 對話方塊。 忽略對話方塊標題（您不會實際傳送立即訊息），並輸入啟用 Lync 的電話號碼：

[![傳送 im] 對話方塊螢幕擷取畫面][(images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "傳送 im] 對話方塊螢幕擷取畫面")

按一下 **[確定]** 之後，Lync Server 會呼叫在對話方塊中輸入的數位。 建立連線之後，您就可以透過啟用 Lync 的手機取得完整的音訊功能，您就能看到完整的會議名單並與之互動。

</div>

<span> </span>

</div>

</div>

</div>

