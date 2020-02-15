---
title: Lync Server 2013： 執行樹系準備
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
ms.openlocfilehash: e9cb09b04ca42c032f042ed7970452f70982e016
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>執行 Lync Server 2013 的樹系準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

您可以使用安裝程式或 Lync Server 管理命令介面指令程式來準備樹系。 準備樹系的 cmdlet 是**Enable-csadforest**。

準備樹系之後，您必須確認通用設定都已複寫之前執行網域準備作業。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>若要使用安裝程式來準備樹系

1.  登入已加入網域的樹系根網域 Enterprise Admins 群組成員身分的電腦。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 [部署精靈。

3.  按一下 **[準備 Active Directory]**，然後等候決定部署狀態。

4.  在**步驟 3： 準備目前樹系**，按一下 [**執行**]。

5.  在 [**準備樹系**] 頁面上，按一下 [**下一步**]。
    
    <div>
    

    > [!NOTE]  
    > 樹系準備可讓您選擇的位置 Lync Server 2013 的萬用群組。 請選擇和組織需求一致的位置。

    
    </div>

6.  在「執行命令」**** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [**動作**] 欄中，依序展開 [**樹系準備**]，並尋找**\<成功\>** 的每一項工作結尾的執行結果，若要確認已順利完成樹系準備，關閉記錄檔，然後按一下 [**完成]**。

8.  等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站列在 [ **Active Directory 站台及服務**嵌入式管理單元中樹系根網域控制站，再執行網域準備作業。 強制導致複寫分鐘內發生的站台內的所有 Active Directory 站台的網域控制站之間的複寫。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>若要使用 cmdlet 準備樹系

1.  登入已加入網域的樹系根網域中 Domain Admins 群組成員身分的電腦。

2.  安裝 Lync Server 核心元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。
    
    2.  如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。
    
    3.  Lync Server 2013 安裝程式] 對話方塊會提示您安裝 Lync Server 檔案的位置。 請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。
    
    4.  在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

4.  執行：
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果您未指定 GroupDomain 參數，預設值為本機網域。 如果不是預設網域的網域中先前建立萬用群組，您必須明確指定 GroupDomain 參數。

5.  等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站列在 [ **Active Directory 站台及服務**嵌入式管理單元中樹系根網域控制站，再執行網域準備作業。

6.  確認樹系準備成功。 執行：
    
        Get-CsAdForest 
    
    此 cmdlet 會傳回的值為**小寫\_FORESTSETTINGS\_狀態\_好**如果樹系準備是否成功。

</div>

<div>

## <a name="see-also"></a>另請參閱


[使用 cmdlet 反向樹系準備 Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[準備樹系的 Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

