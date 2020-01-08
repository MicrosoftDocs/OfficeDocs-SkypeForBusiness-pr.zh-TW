---
title: Lync Server 2013：針對虛擬智慧卡設定 Windows 8
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>針對使用 Lync Server 2013 的虛擬智慧卡設定 Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

部署雙因素驗證與智慧卡技術時，要考慮的一個因素是實施成本。 Windows 8 提供許多新的安全性功能，其中一個最有趣的新功能就是支援虛擬智慧卡。

對於配備符合規範版本1.2 的可信平臺模組（TPM）晶片的電腦，組織現在可以取得智慧卡登入的優點，而不需要在硬體中進行任何額外的投資。 如需詳細資訊，請參閱在[http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)Windows 8 中使用虛擬智慧卡。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>針對虛擬智慧卡設定 Windows 8

1.  使用啟用 Lync 的使用者認證登入 Windows 8 電腦。

2.  在 Windows 8 的 [開始] 畫面中，將游標移至畫面的右下角。

3.  選取 [**搜尋**] 選項，然後搜尋 [**命令提示**字元]。

4.  以滑鼠右鍵按一下**命令提示**字元，然後選取 [以**系統管理員身分執行**]。

5.  執行下列命令以開啟可信平臺模組（TPM）管理主控台：
    
        Tpm.msc

6.  從 TPM 管理主控台，確認您的 TPM 規格版本至少為1。2
    
    <div>
    

    > [!NOTE]  
    > 如果您收到對話方塊，指出找不到相容的信任平臺模組（TPM），請確認電腦有相容的 TPM 模組，且已在系統 BIOS 中啟用。

    
    </div>

7.  關閉 TPM 管理主控台

8.  在命令提示字元中，使用下列命令建立新的虛擬智慧卡：
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 若要在建立虛擬智慧卡時提供自訂 PIN 值，請改為使用/pin 提示。

    
    </div>

9.  在命令提示字元中，執行下列命令以開啟 [電腦管理] 主控台：
    
        CompMgmt.msc

10. 在 [電腦管理] 主控台中，選取 [**裝置管理**]。

11. 展開 [**智慧卡讀取器**]。

12. 確認已成功建立新的虛擬智慧卡讀卡機。

</div>

</div>

<span> </span>

</div>

</div>

</div>

