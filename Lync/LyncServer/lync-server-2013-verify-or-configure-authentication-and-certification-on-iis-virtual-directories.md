---
title: Lync Server 2013：在 IIS 虛擬目錄上確認或設定驗證和憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>在 Lync Server 2013 中的 IIS 虛擬目錄上確認或設定驗證和憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

使用下列程式在您的網際網路資訊服務（IIS）虛擬目錄上設定憑證，或驗證憑證已正確設定。 針對您內部 Lync 伺服器池中的每個執行 IIS 的伺服器，以及選用的控制器或控制器池伺服器，執行下列程式。

<div>


> [!NOTE]  
> 下列程式定義一個程式，以要求在 IIS 中針對所有用途的 Lync Server、內部網站和外部網站，提出所用的合併憑證。 Lync Server 2010 引進了一組 Lync Server 管理命令&nbsp;介面（Windows PowerShell Cmdlet），以管理憑證要求、匯入及作業的快速用途。 此程式假設有一個內部部署的認證機構（CA），可處理該要求。 如果您使用的是適用于 Lync Server 的公用憑證，或您的 CA 需要離線要求，請參閱本主題中的詳細語法，以取得有關– Output 參數的資訊。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虛擬目錄上設定驗證與憑證

1.  若要成功完成下列作業，您必須登入已安裝 web 服務的電腦（前端伺服器或控制器），而且是本機系統管理員。 如果憑證授權單位是貴組織的憑證授權單位，您必須在您要從其申請證書的憑證授權單位上擁有 [**讀取**] 和 [**註冊**] 許可權。 如果您要設定並傳送離線證書要求，則不需要擁有憑證授權單位的許可權。

2.  按一下 [**開始**]，選取 [**所有程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。

3.  在 **[網際網路資訊服務（IIS）管理員**] 中，選取 [**伺服器名稱**]。 在 [**功能] 視圖**中，選取 [**伺服器憑證**]，按一下滑鼠右鍵，然後選取 [**開啟功能**]。
    
    <div>
    

    > [!TIP]  
    > 在 [伺服器憑證功能] 視圖中，如果有指派給伺服器的憑證，就會顯示在這裡。 如果有與 IIS 中外部網站需求相符的憑證，您可以重新使用該憑證。 若要查看憑證，請以滑鼠右鍵按一下憑證，然後選取 [<STRONG>查看 ...]。</STRONG>

    
    </div>

4.  在您要求憑證的前端伺服器或主管中，按一下 [**開始**]，選取 [**所有程式**]，選取 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server Management Shell**]。

5.  在 Lync Server 管理命令介面中，輸入下列內容：
    
        Get-CsCertificate
    
    [輸出] 是電腦個人憑證存放區中目前在伺服器上的憑證清單。 請注意，在結合的憑證（也就是預設、web 服務內部和 web 服務外部使用相同的憑證）中，您會看到 Use 屬性會以預設、WebServicesInternal 和 WebServicesExternal 來填入。 此外，每個使用類型的 Thumbprint 屬性都是相同的。 以下範例顯示 CsCertificate 的輸出範例：
    
    ![目前 scert 狀態的 Get-CsCertificate 資訊](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "目前 scert 狀態的 Get-CsCertificate 資訊")

6.  在 Lync Server 管理命令介面中，輸入下列內容：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    會出現完整命令的位置，如下例所示：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 根據預設，Request CsCertificate 會使用伺服器或池名稱填入 subject 名稱，並以伺服器 FQDN、池 FQDN、簡單的 URL Fqdn 以及內部和外部 web 服務 Fqdn 來填入 subject 替換名稱中的專案。 它會透過參照您部署中的 [拓撲] 檔來執行此動作。 如果缺少值，而且您已指定– Verbose 參數，系統會通知您替換名稱的計算值與實際值不一樣，但不會通知您缺少哪些值。 它會為您提供 Cmdlet 所參照的整個計算值。 在輸出中使用計算出的替換名稱字串，重新要求將包含所有值的新憑證。

    
    </div>
    
    ![使用 Request-CsCertifica 從 cert 要求輸出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用 Request-CsCertifica 從 cert 要求輸出")

7.  在 Lync Server 管理命令介面中，輸入下列內容：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    會出現完整命令的位置，如下例所示：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    CsCertificate Cmdlet 的輸出會顯示相同的憑證（由憑證指紋所識別）會指派給預設、WebServicesExternal 和 WebServicesInternal 用法。
    
    ![IIS WebExt 之 Set-CsCertificate 的輸出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt 之 Set-CsCertificate 的輸出")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>在 IIS 虛擬目錄上驗證或設定驗證與憑證

1.  按一下 [**開始**]，選取 [**所有程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。

2.  在 **[網際網路資訊服務（IIS）管理員**] 中，展開 [**伺服器名稱**]，然後展開 [**網站**]。

3.  以滑鼠右鍵按一下 [ **Lync Server 外部**網站]，然後按一下 [**編輯**系結]

4.  確認 HTTPs 與埠4443相關聯，然後按一下 [ **HTTPs**]。

5.  選取 HTTPS 專案，按一下 [**編輯**]，然後確認 [Lync Server WebServicesExternalCertificate] 已系結至此通訊協定。 比較指紋與 CsCertificate Cmdlet，以確保預期的憑證與 HTTPS 系結正確關聯。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

