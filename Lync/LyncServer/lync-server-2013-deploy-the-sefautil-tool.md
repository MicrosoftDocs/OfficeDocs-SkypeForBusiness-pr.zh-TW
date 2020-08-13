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
ms.openlocfilehash: c37108d8429567c2653174e4d5a9d0510278e4f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SEFAUtil 工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

若要部署及管理群組通話，您必須使用 SEFAUtil 資源套件工具。 工具屬於 Lync Server 2013 資源套件工具。 在您安裝 SEFAUtil 之前，您必須在拓撲中有信任的應用程式集區，並將 SEFAUtil 指定為信任的應用程式，並啟用拓撲。

<div>


> [!IMPORTANT]  
> Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 必須安裝在您計畫執行 SEFAUtil 工具的任何電腦上。



</div>

您可以在部署中的任何前端集區中執行 SEFAUtil。

<div>


> [!NOTE]  
> 如需有關執行 SEFAUtil 的詳細資訊，請參閱 Technet 博客文章：「如何取得 SEFAutil？」？ at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> 。



</div>

<div>

## <a name="to-deploy-sefautil"></a>若要部署 SEFAUtil

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。 如有需要，針對您計畫執行 SEFAUtil 的前端集區定義信任的應用程式集區。 在命令列中執行：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  將 SEFAUtil 工具定義為信任的應用程式。 在命令列中執行：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 如有需要，您可以使用不同的埠。

    
    </div>

5.  使用您的變更來啟用拓撲。 在命令列中執行：
    
        Enable-CsTopology

6.  在您于步驟3建立的受信任應用程式集區中的前端伺服器上，安裝 Lync Server 2013 資源工具組工具。

7.  請確認 SEFAUtil 工具是否運作正常，如下所示：
    
    1.  從具有管理員許可權的 Windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。
        
        <div>
        

        > [!NOTE]  
        > 工具位於 \Program Files\Microsoft Lync Server 2013 \ Reskit。

        
        </div>
    
    2.  顯示使用者的「來電轉接」設定。 在命令列中執行：
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        將會顯示使用者的「來電轉接」設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

