---
title: Lync Server 2013：部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SEFAUtil 工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

若要部署和管理群組呼叫挑選，您需要使用 SEFAUtil 資源套件工具。 此工具是 Lync Server 2013 資源套件工具的一部分。 您必須先在拓撲中擁有受信任的應用程式池，並將 SEFAUtil 指定為信任的應用程式，並啟用拓撲，才能安裝 SEFAUtil。

<div>


> [!IMPORTANT]  
> Microsoft 整合通訊管理 API （UCMA）3.0 核心 SDK 必須安裝在任何您打算執行 SEFAUtil 工具的電腦上。



</div>

您可以在部署的任何前端池中執行 SEFAUtil。

<div>


> [!NOTE]  
> 如需有關執行 SEFAUtil 的詳細資訊，請參閱 Technet 博客文章：「如何取得 SEFAutil 執行？」 at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。



</div>

<div>

## <a name="to-deploy-sefautil"></a>若要部署 SEFAUtil

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。 如有需要，請為您打算執行 SEFAUtil 的前端池定義受信任的應用程式池。 在命令列上執行：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  將 SEFAUtil 工具定義為受信任的應用程式。 在命令列上執行：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 如有需要，您可以使用不同的埠。

    
    </div>

5.  使用您的變更啟用拓撲。 在命令列上執行：
    
        Enable-CsTopology

6.  在您在步驟3中建立之受信任的應用程式池中的前端伺服器上，安裝 Lync Server 2013 資源套件工具。

7.  確認 SEFAUtil 工具正常運作，如下所示：
    
    1.  從具有系統管理員許可權的 Windows 命令提示字元執行該工具，以在您的部署中顯示使用者的來電轉接設定。
        
        <div>
        

        > [!NOTE]  
        > 此工具位於 \Program Files\Microsoft Lync Server 2013 \ Reskit。

        
        </div>
    
    2.  顯示使用者的 [來電轉接] 設定。 在命令列上執行：
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        隨即會顯示使用者的 [來電轉接] 設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

