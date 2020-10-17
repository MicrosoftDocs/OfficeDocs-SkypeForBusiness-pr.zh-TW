---
title: Lync Server 2013：在具有 Lync 功能的電話上使用電話
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
ms.openlocfilehash: 840089b2e65e158086d33f8ebfdfc6828e4e9317
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535820"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>在具有 Lync 功能的電話和 Lync Server 2013 上使用呼叫我

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-09_

Lync 中的「呼叫我」功能可讓使用者使用手機、「土地線」或其他連線到公用交換電話網路 (PSTN) 的裝置，加入會議的音訊部分。 當您嘗試使用 Lync 加入會議時，您通常會看到 [ **加入會議音訊** ] 對話方塊：

![使用 Lync 加入會議音訊視窗螢幕擷取畫面](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入會議音訊視窗螢幕擷取畫面")

如果您選取 [ **呼叫我于**]，則可以從下拉式清單中選取一個電話號碼。 Lync Server 2013 會撥打所選號碼的電話，然後您就可以使用該電話參加會議的音訊部分。

在 [ **Lync –選項**] 對話方塊的 [**電話**] 索引標籤上，您已輸入行動電話、住家電話或其他電話) 的電話號碼 (，會填入下拉式清單：

![Lync 電話設定選項螢幕擷取畫面](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 電話設定選項螢幕擷取畫面")

如果您未在 [ **電話** ] 索引標籤上輸入任何電話號碼，下拉式方塊中將沒有任何可用的號碼。 不過，您可以隨時按一下 [ **新增號碼** ]，讓 Lync Server 撥出至您想要的任何電話號碼：

![Lync 加入會議音訊撥號我視窗螢幕擷取畫面](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入會議音訊撥號我視窗螢幕擷取畫面")

「我的呼叫」功能運作非常好，其方式是讓 Lync Server 呼叫 PSTN 電話號碼，以供您使用。 不過，如果您要求 Lync Server 在 Lync 啟用的端點撥打您的電話，您可以執行到低於最佳的體驗 (例如，在會議室) 中的電話。 以下是您可能遇到的問題，以及解決問題的兩種方式。

若要開始，請在您使用啟用 Lync 功能之電話號碼的電話號碼提供時，執行下列動作。 假設 Ken Myer 嘗試加入會議，讓 Lync Server 呼叫他在1-206-555-1219 （即啟用 Lync 伺服器的電話號碼）。 Ken 最初會連接到會議，但是在幾秒後，Lync 將會顯示郵件 **呼叫未完成或已結束**，且 Ken 會顯示已從會議中移除：

![Lync 通話會議視窗的螢幕擷取畫面](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通話會議視窗的螢幕擷取畫面")

不過，請注意，Lync 交談視窗中有差異。 Ken Myer 是在 [ **參與者** ] 標題底下列出的唯一名稱。 不過，如果您在視窗的標題列中查看，您會看到會議總共有4位參與者。

同樣地，如果您在其他任何會議參與者的 [交談] 視窗中查看，您將不會看到「Ken Myer」列在任何地方：

![Lync 參與者清單視窗螢幕擷取畫面](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 參與者清單視窗螢幕擷取畫面")

此外，Ken Myer 也可以使用其 Lync 啟用的電話，參與通話的音訊部分中。 「我的呼叫」功能實際上已正常運作，但使用者經驗低於最佳。

至少有兩種方法可解決此問題。 如果您已以這種方式加入會議 (例如 Ken Myer) ，您通常可以使用不同的形式來解決此問題。 例如，如果您傳送立即訊息，[交談] 視窗現在會顯示所有會議參與者，包括您：

![Lync 交談和參與者清單螢幕擷取畫面](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 交談和參與者清單螢幕擷取畫面")

此時，您應該能夠以預期的方式參與會議。

或者，您可以變更加入會議的方式，以完全避免這一問題。 如果您需要讓 Lync Server 呼叫啟用 Lync 伺服器的電話，您應該先加入沒有音訊連線的會議。 若要執行此動作，請選取 [加入會議音訊] 對話方塊時，[不要加入音訊] 對話方塊：

![Lync 不加入會議音訊視窗螢幕擷取畫面](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入會議音訊視窗螢幕擷取畫面")

成功連接至會議之後，您現在可以「邀請」 Lync Server 啟用的電話加入會議。 若要這麼做，請將滑鼠放在人脈圖示上，然後按一下 [ **邀請其他人**]：

![Lync 邀請更多參與者視窗螢幕擷取畫面](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀請更多參與者視窗螢幕擷取畫面")

這會顯示 [ **傳送 IM** ] 對話方塊。 忽略對話方塊標題 (實際上不會傳送立即訊息) 並輸入啟用 Lync 功能的電話號碼：

![[傳送 IM] 對話方塊的螢幕擷取畫面](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "[傳送 IM] 對話方塊的螢幕擷取畫面")

按一下 **[確定]** 後，Lync Server 會呼叫在對話方塊中輸入的號碼。 進行連線時，您會透過啟用 Lync 功能的電話獲得完整的音訊功能，而且您將能夠看到完整的會議名單並與其互動。

</div>

<span> </span>

</div>

</div>

</div>

