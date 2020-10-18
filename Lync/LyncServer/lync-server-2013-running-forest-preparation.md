---
title: Lync Server 2013：執行樹系準備
description: Lync Server 2013：執行樹系準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577759"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>對 Lync Server 2013 執行樹系準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備樹系。 準備樹系的 Cmdlet 是 **Enable-CsAdForest**。

準備好樹系之後，您必須在執行網域準備作業之前，先確認全域設定是否已複製。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>若要使用安裝程式來準備樹系

1.  以樹系根域的 Enterprise Admins 群組成員身分登入加入網域的電腦。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動部署嚮導。

3.  按一下 **[準備 Active Directory]**，然後等候決定部署狀態。

4.  在 [ **步驟3：準備目前的樹**系] 中，按一下 [ **執行**]。

5.  在 [ **準備樹** 系] 頁面上，按 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 樹系準備可讓您選擇放置 Lync Server 2013 通用群組的位置。 請選擇和組織需求一致的位置。

    
    </div>

6.  在「執行命令」**** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [ **動作** ] 欄下，展開 [ **樹系準備**]，尋找 **\<Success\>** 每項工作結尾的執行結果，以驗證樹系準備是否順利完成，關閉記錄檔，然後按一下 **[完成]**。

8.  等候 Active Directory 複寫完成，或是強制複寫到樹系根域控制 **站 [Active Directory 網站和服務** ] 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。 強制在所有 Active Directory 網站的網域控制站之間進行複寫，以在幾分鐘內進行網站的複寫。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>若要使用 Cmdlet 準備樹系

1.  以樹系根域的 Domain Admins 群組成員身分登入加入網域的電腦。

2.  安裝 Lync Server 核心元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。
    
    4.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  運行：
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果您未指定 GroupDomain 參數，則預設值為本機網域。 如果通用群組先前是在非預設網域的網域中建立，您必須明確地指定 GroupDomain 參數。

5.  等候 Active Directory 複寫完成，或是強制複寫到樹系根域控制 **站 [Active Directory 網站和服務** ] 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。

6.  確認樹系準備成功。 運行：
    
        Get-CsAdForest 
    
    若樹系準備成功，則此 Cmdlet 會傳回 **LC \_ FORESTSETTINGS \_ 狀態 \_ ** 的值。

</div>

<div>

## <a name="see-also"></a>另請參閱


[使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[準備 Lync Server 2013 的樹系](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

