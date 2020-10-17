---
title: 指派伺服器對伺服器驗證憑證至 Lync Server 2013
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
ms.openlocfilehash: ec8ac614cdc829ab2b1efd7d6ff9179c33d5a33e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499470"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="fe5e6-102">將伺服器對伺服器驗證憑證指派給 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe5e6-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe5e6-103">_**主題上次修改日期：** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="fe5e6-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="fe5e6-104">若要判斷伺服器對伺服器驗證憑證是否已指派給 Microsoft Lync Server 2013，請從 Lync Server 2013 管理命令介面執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fe5e6-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="fe5e6-105">若未傳回憑證資訊，您必須指派 token 簽發者憑證，才能使用伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="fe5e6-106">一般來說，任何 Lync Server 2013 憑證可以做為 OAuthTokenIssuer 憑證，也可以用來做為您的憑證。例如，您的 Lync Server 2013 預設憑證也可以當成 OAuthTokenIssuer 憑證使用。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fe5e6-107"> (OAUthTokenIssuer 憑證也可以是任何網頁伺服器憑證，包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。 ) 伺服器對伺服器驗證所用之憑證的主要兩項需求如下： 1) 相同的憑證必須設定為所有前端伺服器上的 OAuthTokenIssuer 憑證;而且，2) 憑證必須至少是2048位。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="fe5e6-108">如果您沒有可用於伺服器對伺服器驗證的憑證，您可以取得新的憑證，匯入新的憑證，然後使用該憑證進行伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="fe5e6-109">在要求並取得新憑證之後，您可以登入任何一部前端伺服器，並使用與下列類似的 Windows PowerShell 命令，匯入並指派該憑證：</span><span class="sxs-lookup"><span data-stu-id="fe5e6-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="fe5e6-110">在上述命令中，Path 參數會代表憑證檔案的完整路徑，而 Password 參數則代表指派給憑證的密碼。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="fe5e6-111">此程式應該只執行一次： Lync Server 的複寫服務會自動建立一組排程的工作，將憑證解密並部署至您的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="fe5e6-112">或者，您可以使用現有憑證做為伺服器對伺服器驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="fe5e6-113"> (所述，可將預設憑證當做伺服器對伺服器驗證憑證使用。 ) 下列一對 Windows PowerShell 命令可取得預設憑證的 Thumbprint 屬性值，然後使用該值將預設憑證設為伺服器對伺服器驗證憑證：</span><span class="sxs-lookup"><span data-stu-id="fe5e6-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="fe5e6-114">在上述命令中，所檢索的憑證會設定為以全域伺服器對伺服器驗證憑證的形式運作;這表示憑證將會複製到並由所有前端伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="fe5e6-115">同樣地，此命令只會執行一次，且只能在其中一部前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="fe5e6-116">雖然所有前端伺服器都必須使用相同的憑證，但您不應該在每個前端伺服器上設定 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="fe5e6-117">請改為設定憑證一次，然後讓 Lync Server 的複寫伺服器負責將該憑證複製到每個伺服器。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="fe5e6-118">Set-CsCertificate Cmdlet 會採取問題的憑證，並立即設定該憑證充當目前的 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fe5e6-119"> (Lync Server 2013 可保留兩個憑證類型的副本：目前的憑證和舊的憑證。 ) 如果您需要新的憑證立即開始充當 OAuthTokenIssuer 的憑證，則您應該使用 Set-CsCertificate Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="fe5e6-120">您也可以使用 Set-CsCertificate Cmdlet 來「推出」新的憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="fe5e6-121">「滾動」憑證只是表示您將新的憑證設定為在指定的時間點成為目前的 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="fe5e6-122">例如，此命令會檢索預設憑證，然後設定該憑證作為目前的 OAuthTokenIssuer 憑證，在2012年7月1日為止。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="fe5e6-123">在2012年7月1日，會將新的憑證設定為目前的 OAuthTokenIssuer 憑證，而將「舊」 OAuthTokenIssuer 憑證設定為舊版憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="fe5e6-124">如果您不想要使用 Windows PowerShell 您也可以使用憑證 MMC 主控台從一部前端伺服器匯出憑證，然後在其他所有的前端伺服器上匯入該相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="fe5e6-125">如果您這麼做，請確定匯出私密金鑰和憑證本身。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="fe5e6-126">在此情況下，必須在每一部前端伺服器上執行該程式。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="fe5e6-127">以這種方式匯出及匯入憑證時，Lync Server 2013 不會將該憑證複製到每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="fe5e6-128">將憑證匯入至所有前端伺服器後，即可使用 Lync Server 部署嚮導（而非 Windows PowerShell）來指派該憑證。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="fe5e6-129">若要使用部署嚮導指派憑證，請在已安裝部署嚮導的電腦上完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fe5e6-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="fe5e6-130">依序按一下 [開始]、[所有程式]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync Server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="fe5e6-131">在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="fe5e6-132">在 [Microsoft Lync Server 2013] 頁面上，按一下 [標題**步驟3：要求、安裝或指派憑證**] 底下的 [**執行**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="fe5e6-133"> (注意：如果您已在此電腦上安裝憑證，則會將 [ **執行** ] 按鈕重新標示為 [ **執行**中]。 ) </span><span class="sxs-lookup"><span data-stu-id="fe5e6-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="fe5e6-134">在 [憑證] 嚮導中，選取 **OAuthTokenIssuer** 憑證，然後按一下 [ **指派**]。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="fe5e6-135">在 [憑證指派] 嚮導的 [ **憑證指派** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="fe5e6-136">在 [ **憑證存放區** ] 頁面上，選取要用於伺服器對伺服器驗證的憑證，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="fe5e6-137">在 [憑證指派摘要] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="fe5e6-138">在 [執行命令] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="fe5e6-139">關閉憑證嚮導和部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="fe5e6-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

