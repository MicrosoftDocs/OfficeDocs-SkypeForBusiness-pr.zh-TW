---
title: Lync Server 2013：準備 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c5d83acbe32d33a235e7c2918663340a3ac7ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>在 Lync Server 2013 中準備 Active Directory 網域服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-19_

在 Lync Server 2013 中，您可以使用 Lync Server 部署嚮導來準備 Active Directory 網域服務，也可以直接使用 Lync Server 管理命令介面 Cmdlet。 您也可以直接在網域控制站上使用 ldifde.exe 命令列工具，如本主題稍後所述。

Lync Server 部署嚮導會引導您完成每個 Active Directory 準備工作。 部署嚮導會執行 Lync Server 管理命令介面 Cmdlet。 這項工具對於具有單一網域和單一樹系拓撲的環境，或是其他相似拓撲的環境，都很有用，

<div>


> [!IMPORTANT]  
> 您可以在樹系或網域中部署 Lync Server，其中的網域控制站會執行32位版本的部分作業系統 (如需詳細資訊，請參閱<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync server 2013) 的 Active Directory 基礎結構需求</A>。 不過，您無法使用 Lync Server 部署嚮導執行這些環境中的架構、樹系和網域準備工作，因為部署嚮導和支援檔只是64位。 但您可以在 32 位元的網域控制站上使用 ldifde.exe 與相關聯的 .ldf 檔案，進行架構、樹系與網域的準備工作。 請參閱本主題稍後的＜使用 Cmdlet 和 Ldifde.exe＞一節。



</div>

您可以使用 Lync Server 管理命令介面 Cmdlet，以遠端方式或更複雜的環境執行工作。

<div>

## <a name="active-directory-preparation-prerequisites"></a>準備 Active Directory 的先決條件

您必須在執行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 的電腦上執行 Active Directory 準備步驟，SP1 (64 位) 。 Active Directory 準備工作需要 Lync Server 管理命令介面和 Ocscore.msi。

以下是執行 Active Directory 準備工作時所需的元件：

  - Lync Server 核心元件 ( # A0) 
    
    <div>
    

    > [!NOTE]  
    > 如果您打算使用 Lync Server 管理命令介面進行 Active Directory 準備，您必須先執行 Lync Server 部署嚮導，以安裝核心元件。

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > 若為 Windows Server 2012 和 Windows Server 2012 R2，您可以使用伺服器管理員安裝和啟動 .NET Framework 4.5。 如需詳細資訊，請參閱<A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他軟體需求</A>中的「Microsoft .net Framework 4.5」。 若為 Windows Server &nbsp; 2008 &nbsp; R2，請從 Microsoft 網站下載並安裝<A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A> 。

    
    </div>

  - 遠端伺服器管理工具 (RSAT)
    
    <div>
    

    > [!NOTE]  
    > 如果您在網域控制站以外的成員伺服器上執行 Active Directory 準備步驟，則需要某些 RSAT 工具。 從 [伺服器管理員] 的 [AD DS] 和 [AD LDS 工具] 節點，安裝適用于 Windows PowerShell 的 AD DS 嵌入式管理單元和命令列工具和 Active Directory 模組。

    
    </div>

  - Microsoft Visual c + + 11 可轉散發元件
    
    <div>
    

    > [!NOTE]  
    > 如果電腦尚未安裝此必要套件，安裝程式會提示您加以安裝。此套件會隨附給您，您不需另行取得。

    
    </div>

  - Windows PowerShell 3.0 (64-位) 
    
    若為 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 應隨附在 Lync Server 2013 安裝中。 若為 Windows Server 2008 R2，您必須安裝或升級至 Windows PowerShell 3.0。 如需詳細資訊，請參閱[安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>系統管理員的權限與角色

下表說明每一項 Active Directory 準備工作所需的系統管理權限和角色。

### <a name="user-rights-required-for-active-directory-preparation"></a>準備 Active Directory 時所需的使用者權限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>程式</th>
<th>權限或角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>架構準備</p></td>
<td><p>樹系根網域的 Schema Admins 群組成員，以及架構主機的系統管理員權限</p></td>
</tr>
<tr class="even">
<td><p>樹系準備</p></td>
<td><p>樹系的 Enterprise Admins 群組成員</p></td>
</tr>
<tr class="odd">
<td><p>網域準備</p></td>
<td><p>所指定網域的 Enterprise Admins 或 Domain Admins 群組成員</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>準備 Active Directory 時使用的 Cmdlet

下表比較 Lync Server 管理命令介面 Cmdlet，用來準備 AD DS，以用於在 Microsoft Office 通訊伺服器 2007 R2 中準備 AD DS 的 LcsCmd 命令。

### <a name="cmdlets-compared-to-lcscmd"></a>各 Cmdlet 與 LcsCmd 的比較

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>鎖定 Active Directory 的需求

如果您的組織中已停用權限繼承，或必須停用已驗證的使用者權限，則您在進行網域準備時需要執行額外的步驟。 如需詳細資訊，請參閱[在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

<div>

## <a name="custom-container-permissions"></a>自訂容器權限

如果您的組織使用的是自訂容器，而非三個內建的容器 (也就是使用者、電腦和網域控制站)，您就必須將自訂容器的讀取存取權授與 Authenticated Users 群組。 執行網域準備工作時，必須要有容器的讀取存取權。 如需詳細資訊，請參閱[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)。

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>使用 Cmdlet 和 Ldifde.exe

Lync Server 部署嚮導和**Install-CsAdServerSchema** Cmdlet 中的 [**準備架構**] 步驟會延伸執行64位作業系統的網域控制站上的 Active Directory 架構。 如果您需要在執行 32 位元作業系統的網域控制站上擴充 Active Directory 架構，可以遠端從成員伺服器執行 **Install-CsAdServerSchema** Cmdlet (建議方法)。 如果您需要直接在網域控制站上執行架構準備工作，可以使用 Ldifde.exe 工具匯入架構檔案。 大多數的 Windows 作業系統版本皆會提供 Ldifde.exe 工具。

如果您使用 Ldifde.exe 匯入架構檔案，則無論您在從舊版進行移轉，還是執行全新安裝，都必須將四個檔案全部匯入。您必須依下列順序加以匯入：

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf

<div>


> [!NOTE]  
> 這四個 .ldf 檔案皆位於安裝媒體或下載位置的 \Support\Schema 目錄中。



</div>

若要使用 Ldifde.exe 在作為架構主機的網域控制站上匯入這四個架構檔案，請使用下列格式：

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

例如：

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> 只有當您以不同的使用者身分登入時，才應使用 b 參數。如需必要使用者權限的詳細資訊，請參閱本主題稍早的＜系統管理員的權限與角色＞一節。



</div>

若要使用 Ldifde.exe 在不是架構主機的網域控制站上匯入這四個架構檔案，請使用下列格式：

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

如需使用 Ldifde 的詳細資訊，請參閱 Microsoft 知識庫文章237677：「使用 LDIFDE 匯入及匯出目錄物件至 Active Directory」 at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204) 。

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中準備 Active Directory 架構](lync-server-2013-preparing-the-active-directory-schema.md)

  - [準備 Lync Server 2013 的樹系](lync-server-2013-preparing-the-forest.md)

  - [準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

