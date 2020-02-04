---
title: Lync Server 2013：執行網域準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 408dea780b4136f86ffed30d199d1d0ee63d6821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>為 Lync Server 2013 執行網域準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-16_

您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備網域。 準備網域的 Cmdlet 為**Enable-CsAdDomain**。

[網域準備] 是為 Lync Server 2013 準備 Active Directory 網域服務的最後一個步驟。

<div>

## <a name="to-use-setup-to-prepare-domains"></a>使用安裝程式準備網域

1.  以網域系統管理員群組的成員身分登入網域中的任何伺服器。

2.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。

3.  按一下 [準備 Active Directory]****，然後等候決定部署狀態。

4.  在 [步驟 5：準備目前的網域]****，按一下 [執行]****。

5.  在 [**準備網域**] 頁面上，按一下 **[下一步]**。

6.  在 [執行命令]**** 頁面上，尋找 [工作狀態：完成]****，然後按一下 [檢視記錄檔]****。

7.  在 [**動作**] 欄底下，展開 [**網域準備**]，尋找每個工作** \< \> **結尾的成功執行結果，確認已成功完成 [網域準備]，然後關閉記錄，然後按一下 **[完成]**。

8.  等待 Active Directory 複製完成，或強制複製到林中根網網域控制站之 Active Directory 網站和服務管理單元中列出的所有網網域控制站。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>使用 Cmdlet 準備網域

1.  以網域系統管理員群組的成員身分登入網域中的任何伺服器。

2.  安裝 Lync Server Core 元件，如下所示：
    
    1.  從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。
    
    2.  如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。
    
    3.  [Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。 選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。
    
    4.  在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。 安裝程式會安裝 Lync Server 2013 核心元件。

3.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  用盡
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    例如：
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    如果您沒有指定 Domain 參數，則預設為本地域。

5.  確認網域準備順利完成。 用盡
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    例如：
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > [參數 GlobalSettingsDomainController] 可讓您指出儲存全域設定的位置。 如果您的設定是儲存在系統容器中（這通常是將未將全域設定遷移至配置容器的升級部署），您可以在 Active Directory 目錄林的根目錄中定義網網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 AD&nbsp;DS 中的任何網網域控制站。

    
    </div>
    
    如果您沒有指定**Domain**參數，則預設為本地域。
    
    如果網域準備成功，這個**Cmdlet\_就\_會\_傳回 LC DOMAINSETTINGS 狀態**的值。

</div>

<div>

## <a name="see-also"></a>請參閱


[將 Cmdlet 用於 Lync Server 2013 的反向網域準備](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[針對 Lync Server 2013 準備網域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

