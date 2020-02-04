---
title: Lync Server 2013：執行樹系準備
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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>針對 Lync Server 2013 執行樹系準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備目錄林。 準備林的 Cmdlet 是**Enable-CsAdForest**。

準備好林之後，您必須先確認全域設定已先進行複製，然後再執行網域準備作業。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>使用安裝程式準備林

1.  登入加入網域的電腦，作為林根網域之 [企業系統管理員] 群組的成員。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動部署嚮導。

3.  按一下 [準備 Active Directory]****，然後等候決定部署狀態。

4.  在**步驟3：準備目前的林**，按一下 [**執行**]。

5.  在 [**準備林**] 頁面上，按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > [林準備] 可讓您選擇要放置 Lync Server 2013 通用群組的位置。 請選擇和組織需求一致的位置。

    
    </div>

6.  在 [執行命令] **** 頁面上，尋找 [工作狀態: 已完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [**動作**] 欄底下，展開 [**林準備**]，尋找每個工作結尾的** \<成功\> **執行結果，確認已成功完成 [目錄林準備]，然後關閉記錄，然後按一下 **[完成]**。

8.  在執行網域準備前，請等候 Active Directory 複製完成，或強制複製到林中根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。 在所有 Active Directory 網站的網網域控制站之間強制進行複製，以在幾分鐘內進行複製。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>使用 Cmdlet 準備林

1.  以網域管理員群組的成員身分登入加入網域的電腦（在林根網域中）。

2.  安裝 Lync Server Core 元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。
    
    4.  在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  用盡
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果您沒有指定 GroupDomain 參數，則預設值為本地域。 如果通用群組是先前在非預設網域的網域中建立，您必須明確指定 GroupDomain 參數。

5.  在執行網域準備前，請等候 Active Directory 複製完成，或強制複製到林中根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。

6.  確認林準備已成功完成。 用盡
    
        Get-CsAdForest 
    
    如果林準備成功，這個 Cmdlet 會傳回**\_LC FORESTSETTINGS\_狀態\_** 的值。

</div>

<div>

## <a name="see-also"></a>請參閱


[使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[為 Lync Server 2013 準備樹系](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

