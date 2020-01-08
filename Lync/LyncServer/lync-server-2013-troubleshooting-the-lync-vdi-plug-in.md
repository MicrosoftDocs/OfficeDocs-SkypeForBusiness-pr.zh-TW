---
title: Lync Server 2013：疑難排解 Lync VDI 外掛程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>在 Lync Server 2013 中疑難排解 Lync VDI 外掛程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>在瘦用戶端上安裝 Lync VDI 外掛程式的疑難排解問題

如果您在瘦用戶端上安裝 VDI 外掛程式時會發生問題，請檢查下列專案：

  - 確定您在 TEMP 及 TMP 系統變數中指定的資料夾中有足夠的空間。

  - 確定已關閉 [防寫] 功能。 如需相關指示，請參閱您的裝置製造商的檔。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>對配對問題進行疑難排解

當 VDI 外掛程式配對失敗時，右下角的配對圖示會顯示為紅色的 [X]，如下所示：

![LYNC vdi 圖示，顯示成功]配對的(images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "lync vdi 圖示顯示成功配對")

下列是失敗的可能原因，以及您可以採取的修正動作。

  - **使用者在登入期間輸入的認證不正確。**
    
    使用者應該登出 Lync，然後使用正確的認證重新登入。 [配對] 對話方塊會再次出現，並顯示配對是否成功。

  - **遠端桌面用戶端的另一個實例正在執行。**
    
    如果他們是在 Windows 中使用 [遠端桌面連線]，使用者就應該執行下列動作：
    
    1.  啟動 [工作管理員]：按**Alt + Ctrl + Delete**，然後按一下 [**啟動工作管理員**]。
    
    2.  按一下 [**處理**程式] 索引標籤，然後在清單中尋找所有名為**mstsc**的進程。
    
    3.  醒目提示每個**mstsc**程式，然後按一下 [**結束處理**程式]。
    
    4.  啟動新的遠端桌面會話，然後再次嘗試連線。

  - **無法正確安裝所需的檔案。**
    
    在本機電腦上安裝外掛程式之後，下列檔案應該出現在 C：\\Program Files\\Microsoft Office\\office 15 （或適當的磁片磁碟機號）下：
    
      - LyncVdiPlugin
    
      - UcVdi
    
    如果 VDI 配對有任何問題，請檢查以確定本機電腦上是否有這些檔案。

  - **Lync 用戶端正在本機電腦上執行。**
    
    若要使用 Lync VDI 外掛程式，不一定要在本機電腦上執行 Lync 用戶端，否則配對將會失敗。 最佳做法是，使用者不應該在本機電腦上安裝 Lync 用戶端。

</div>

</div>

<span> </span>

</div>

</div>

</div>

