---
title: Lync Server 2013： 確認或 IIS 虛擬目錄上設定驗證與憑證
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
ms.openlocfilehash: b4a9e4b2ad53b3fa3a339eae7b4b1ee1f4412548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>確認或 Lync Server 2013 中的 IIS 虛擬目錄上設定驗證與憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-05-25_

使用下列程序在網際網路資訊服務 (IIS) 虛擬目錄上設定憑證或確認已正確設定憑證。 每個執行 IIS 內部 Lync 伺服器集區中的伺服器和選擇性的 Director.or Director 集區伺服器上執行下列程序。

<div>


> [!NOTE]  
> 下列程序定義要求合併的憑證用於所有目的 Lync Server、 內部網站及外部網站的 IIS 中的程序。 Lync Server 2010 引進了 Lync Server 管理命令介面的一組&nbsp;的快速的目的，是管理憑證要求、 匯入，以及工作分派的 Windows PowerShell cmdlet。 程序中假設有內部部署的憑證授權單位 (CA) 可處理要求。 如果您的 Lync Server 用途，或您的 CA 需要離線要求，您可以使用公用憑證，請參閱本主題的資訊中的詳細的語法 – 輸出參數。 <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-cscertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>設定 IIS 虛擬目錄上的驗證及憑證

1.  若要順利完成下列，您必須登入電腦 （前端伺服器或 Director） 其中的 web 服務會安裝，且是本機系統管理員。 對於將向其要求憑證的憑證授權單位，您必須擁有該憑證授權單位的「讀取」**** 和「註冊」**** 權限。 如果將設定並傳送離線憑證要求，則不需要對憑證授權單位的權限。

2.  按一下 **[開始]**，選取 **[所有程式]**、**[系統管理工具]**，然後按一下 **[Internet Information Services (IIS) 管理員]**。

3.  在 **[Internet Information Services (IIS) 管理員]** 中，選取 **[伺服器名稱]**。在 **[功能檢視]** 中，選取 **[伺服器憑證]**，按右鍵並選取 **[開啟功能]**。
    
    <div>
    

    > [!TIP]  
    > 在 [伺服器憑證功能檢視] 中，如果有憑證指派給伺服器，將會在此顯示。如果有憑證符合 IIS 中 External Web Site 的要求，可以重複使用該憑證。要檢視憑證，在憑證按右鍵並選取 <STRONG>[檢視...]</STRONG>。

    
    </div>

4.  在前端伺服器或為其要求的憑證的 Director 上，按一下 [**開始]**，請選取 [**所有程式]**、 選取 [ **Microsoft Lync Server 2013**中，和 [ **Lync Server 管理命令介面**。

5.  在 [Lync Server 管理命令介面中，輸入下列命令：
    
        Get-CsCertificate
    
    輸出為目前在伺服器上電腦個人憑證存放區中的憑證清單。請注意：在組合憑證中 (亦即預設 Web 服務內部及 Web 服務外部使用相同的憑證)，「使用」屬性會填入 Default, WebServicesInternal 及 WebServicesExternal。每個「使用」類型也會有相同的「指紋」屬性。以下範例顯示 Get-CsCertificate 的輸出範例：
    
    ![Get-cscertificate 目前 scert 狀態資訊](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-cscertificate 目前 scert 狀態資訊")

6.  在 [Lync Server 管理命令介面中，輸入下列命令：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    完整命令將類似下列範例：
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 依預設，Request-CsCertificate 會在主體名稱中填入伺服器或集區名稱，並且在主體替代名稱的項目中填入伺服器 FQDN、集區 FQDN、簡單 URL FQDN 以及內部與外部 Web 服務 FQDN。這是透過參考部署中的拓撲文件。如果缺少某個值，而且指定了–Verbose 參數，將會通知您別名的計算值與實際值不同，但不會告知缺少哪些值，不過會提供您 Cmdlet 參考的整個計算值。可使用輸出中的計算別名字串，重新要求會包含所有值的新憑證。

    
    </div>
    
    ![使用要求 CsCertifica 的憑證要求的輸出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用要求 CsCertifica 的憑證要求的輸出")

7.  在 [Lync Server 管理命令介面中，輸入下列命令：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    完整命令將類似下列範例：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate Cmdlet 的輸出會顯示相同的憑證 (以憑證指紋識別) 已指派給 Default, WebServicesExternal 及 WebServicesInternal 使用。
    
    ![在 IIS WebExt Set-cscertificate 的輸出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "在 IIS WebExt Set-cscertificate 的輸出")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>確認或設定 IIS 虛擬目錄的驗證與憑證

1.  按一下 **[開始]**，選取 **[所有程式]**、[系統管理工具]****，然後按一下 **[Internet Information Services (IIS) 管理員]**。

2.  在**網際網路資訊服務 (IIS) 管理員**] 中，依序展開 [**伺服器名稱**，，然後展開 [**站台**。

3.  用滑鼠右鍵按一下 **[Lync Server External Web Site]**，然後按一下 **[編輯繫結]**。

4.  確認 https 關聯至連接埠 4443，然後按一下 **[https]**。

5.  選取 [HTTPS] 項目，按一下 [**編輯**]，然後確認 [Lync Server WebServicesExternalCertificate 繫結至此通訊協定。 與來自 Set-CsCertificate Cmdlet 的指紋比較，確認預期的憑證已正確與 HTTPS 繫結關聯。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

