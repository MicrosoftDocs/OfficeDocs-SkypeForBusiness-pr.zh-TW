---
title: 將伺服器對伺服器驗證憑證指派給 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbead49c200ab1b679ef9b4ffa3d9b03bb72cd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>將伺服器對伺服器驗證憑證指派給 Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-10-24_

若要判斷伺服器對伺服器驗證憑證已指派給 Microsoft Lync Server 2013，請從 Lync Server 2013 管理命令介面中執行下列命令：

    Get-CsCertificate -Type OAuthTokenIssuer

如果沒有憑證資訊會傳回您必須指派權杖簽發者憑證，您才能使用伺服器對伺服器驗證。 一般而言，Lync Server 2013 中的任何憑證可以做為 OAuthTokenIssuer 憑證;例如，Lync Server 2013 預設憑證也可用為 OAuthTokenIssuer 憑證。 （[OAUthTokenIssuer] 憑證也可以是任何的網頁伺服器憑證主旨] 欄位中包含的 SIP 網域名稱）。用於伺服器對伺服器驗證憑證的主要兩個需求是這些： 1) 相同的憑證必須設定為在所有前端伺服器; 上的 [OAuthTokenIssuer] 憑證和，2） 的憑證必須至少 2048 位元。

如果您不需要的憑證，可用於伺服器對伺服器驗證，您可以取得新的憑證，匯入新的憑證，並再將該憑證用於伺服器對伺服器驗證。 您要求並取得新的憑證後您可以然後登入為任何一個前端伺服器並使用類似這樣的 Windows PowerShell 命令來匯入與指派的憑證：

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

在上述命令路徑參數會代表的完整路徑憑證的檔案，而 Password 參數表示已指派給憑證的密碼。 只要一次應該執行此程序： Lync Server 複寫服務會再自動建立一組的排程工作，解密，並將憑證部署至所有前端伺服器。

或者，您可以使用現有的憑證作為您的伺服器對伺服器驗證憑證。 （如所述的預設憑證可以當做的伺服器對伺服器驗證憑證。）下列 Windows PowerShell 命令的配對擷取預設憑證的指紋屬性的值，然後使用該值進行憑證的伺服器對伺服器驗證憑證的預設值：

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

在上述命令中，擷取的憑證設為擔任的全域伺服器對伺服器驗證憑證。這表示憑證會複寫至，並供所有前端伺服器。 同樣地，一次，並只在一個前端伺服器，應只有執行此命令。 雖然所有前端伺服器必須使用相同的憑證，則不應在每部前端伺服器上設定的 OAuthTokenIssuer 憑證。 相反地，一次設定憑證，然後讓 Lync Server 複寫伺服器負責處理的每一部伺服器來複製該憑證。

Set-cscertificate cmdlet 會採用憑證有問題，並立即將設定做為目前的 OAuthTokenIssuer 憑證的憑證。 (Lync Server 2013 會保留兩個副本的憑證類型： 目前的憑證與先前的憑證。)如果您需要新的憑證，若要立即開始做為 [OAuthTokenIssuer] 憑證，您應該使用 Set-cscertificate cmdlet。

您也可以使用 Set-cscertificate cmdlet 來 「 部署 」 的新憑證。 「 啟用 」 的憑證就是指您設定新的憑證，在時間中成為目前的 OAuthTokenIssuer 憑證，在指定的點。 例如，此指令擷取 default 憑證，並再設定憑證作為目前的 OAuthTokenIssuer 憑證自 2012 年 7 月 1 日起接管：

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

在 2012 年 7 月 1 日的新憑證會被設做目前的 OAuthTokenIssuer 憑證和 「 舊 」 的 OAuthTokenIssuer 憑證會被設做先前的憑證。

如果您不想要使用 Windows PowerShell 您也可以使用 [憑證] MMC 主控台來從一部前端伺服器匯出憑證，然後在所有其他前端伺服器上匯入該相同的憑證。 如果您這麼做，請確定您匯出私密金鑰] 以及本身的憑證。

<div>


> [!WARNING]
> 在此情況下，必須在每部前端伺服器上執行程序。 當匯出和匯入憑證，在這種方式 Lync Server 2013 中的將不會複製該憑證至每個前端伺服器。



</div>

所有前端伺服器已匯入憑證之後，就可以指派該憑證而不是 Windows PowerShell 中使用 Lync Server 部署精靈。 若要將憑證指派藉由使用 [部署精靈，完成下列步驟在已安裝 [部署精靈在電腦上：

1.  按一下 [開始]、 [所有程式]、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 部署精靈**。

2.  在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。

3.  在 [Microsoft Lync Server 2013] 頁面上，按一下 [**執行**] 按鈕標題底下的**步驟 3： 要求、 安裝或指派憑證**。 (請注意： 如果您已經在此電腦上安裝憑證，然後**再執行一次**會標示 [**執行**] 按鈕。)

4.  在 [憑證] 精靈中，選取 [ **OAuthTokenIssuer** ] 憑證，然後按一下 [**指派**。

5.  在 [憑證指派精靈] 在 [**憑證指派**] 頁面上，按一下 [**下一步**]。

6.  在 [**憑證存放區**] 頁面上，選取的憑證用於伺服器對伺服器驗證，然後按一下 [**下一步**。

7.  在 [憑證指派摘要] 頁面上，按 **[下一步]**。

8.  在 [執行命令] 頁面上，按一下 **[完成]**。

9.  關閉 [憑證精靈] 及 [部署精靈]。

</div>

<span> </span>

</div>

</div>

</div>

