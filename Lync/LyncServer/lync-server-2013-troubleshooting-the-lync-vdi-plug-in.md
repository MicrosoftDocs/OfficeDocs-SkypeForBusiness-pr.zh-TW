---
title: Lync Server 2013： 疑難排解 Lync VDI 外掛程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d75e0801ec16957083f2e9fef043080c771ea9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>疑難排解 Lync VDI 外掛程式 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>疑難排解在精簡型用戶端上安裝 Lync VDI 外掛程式的問題

如果在精簡型用戶端上安裝 VDI 外掛程式時發生問題，請檢查下列各項：

  - 確定您在 TEMP 和 TMP 系統變數中指定的資料夾中有足夠的空間。

  - 確定已關閉防寫保護。請參閱裝置製造商的文件，以取得指示。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>疑難排解配對問題

當 VDI 外掛程式配對失敗時，右下的配對圖示會顯示成紅色的 “X”，如下所示：

![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")

以下是失敗的可能原因，以及您可以採取的更正動作。

  - **使用者在登入時輸入不正確的憑證。**
    
    使用者應該登出 Lync，然後再使用正確的認證登入。 配對對話方塊會重新出現，並顯示配對是否成功。

  - **有另一個遠端桌面用戶端執行個體正在執行中。**
    
    如果他們在 Windows 中使用遠端桌面連線，使用者應該執行下列命令：
    
    1.  啟動工作管理員：按 **Alt+Ctrl+Delete** 鍵，然後按一下 [啟動工作管理員]****。
    
    2.  按一下 [程序]**** 索引標籤，在清單中尋找名為 **mstsc.exe** 的所有程序。
    
    3.  將每個 **mstsc.exe** 程序醒目提示，然後按一下 [結束處理程序]****。
    
    4.  啟動新的遠端桌面工作階段，並重試連線。

  - **必要檔案安裝不正確。**
    
    外掛程式安裝在本機電腦上之後，下列檔案應出現 [c:\\Program Files\\Microsoft Office\\Office15 （或適當的磁碟機代號）：
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    如果 VDI 配對有任何問題，請檢查並確定這些檔案存在於本機電腦上。

  - **Lync 用戶端正在本機電腦上執行。**
    
    若要使用的 Lync VDI 外掛程式，Lync 用戶端必須未執行的本機電腦，否則配對將會失敗。 最佳作法是，使用者不應該安裝 Lync 用戶端的本機電腦上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

