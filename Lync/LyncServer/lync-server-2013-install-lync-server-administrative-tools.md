---
title: Lync Server 2013：安裝 Lync Server 系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>安裝 Lync Server 2013 系統管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本主題說明如何安裝您需要用來部署和管理 Lync Server 2013 的管理工具。 預設會在執行 Lync Server 2013 的每個伺服器上安裝 [管理工具]。 此外，您還可以在其他電腦上安裝系統管理工具，例如專用的系統管理主控台。 我們強烈建議您在與您建立的 Lync Server 2013 部署相同網域或林中的電腦上安裝系統管理工具，因為如此一來，請確定 Active Directory 網域服務準備步驟已[完成]，可讓您稍後在該電腦上使用系統管理工具發佈拓撲。

在安裝或使用 Lync Server 2013 系統管理工具之前，請務必先審查基礎結構、作業系統、軟體及系統管理員許可權需求。 如需基礎結構需求的詳細資料，請參閱[Lync Server 2013 中的管理工具基礎結構需求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 如需有關安裝 Lync Server 2013 系統管理工具的作業系統和軟體需求的詳細資料，請參閱 lync [server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)，以及[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)。 如需有關安裝及使用工具所需的使用者權利和許可權的詳細資訊，請參閱[安裝和管理 Lync Server 2013 所需的系統管理員權利和許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。

<div>


> [!IMPORTANT]  
> 如果您的組織要求您在系統磁片磁碟機以外的磁碟機上找到 [網際網路資訊服務（IIS）] 和 [所有 Web 服務]，您可以在 [設定] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑（包括 OCSCore），其餘的 Lync Server 2013 檔案也會部署到這個磁片磁碟機。



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>若要安裝 Lync Server 2013 系統管理工具

1.  以本機系統管理員（最小需求）登入您想要安裝管理工具的電腦。 如果您是在 Windows Vista 或 Windows 7 作業系統上以標準使用者身分登入，且已啟用使用者帳戶控制（UAC），系統會提示您輸入本機系統管理員或網域對等的使用者名稱和密碼。

2.  在您的電腦上找出安裝媒體，然後按兩下 [ \\Setup\\amd64\\setup.exe]。

3.  如果系統提示您安裝 Microsoft Visual c + + 2008 可發佈專案，請按一下 **[是]**。

4.  在 [ **Microsoft Lync Server 2013 安裝位置**] 頁面上，按一下 **[確定]**。 如果您需要將檔案安裝至其他位置，請將此路徑變更為其他位置或磁片磁碟機。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的組織要求您在系統磁片磁碟機以外的磁碟機上找到 [網際網路資訊服務（IIS）] 和 [所有 Web 服務]，您可以在 [設定] 對話方塊中變更 Lync Server 2013 檔案的安裝位置路徑。 如果您將安裝檔案安裝到此路徑，包括 OCSCore，則其餘的 Lync Server 2013 檔案也會部署到此磁片磁碟機。

    
    </div>

5.  在 [**使用者授權合約**] 頁面上，查看 [授權條款]，按一下 [**我接受**]，然後按一下 **[確定]**。 您必須先執行此步驟，才能繼續進行。

6.  在 [ **Microsoft Lync Server 2013 –部署嚮導]** 頁面上，按一下 [**安裝管理員工具**]。

7.  安裝順利完成後，**請按一下 [** 結束]。

</div>

<div>

## <a name="see-also"></a>請參閱


[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

