---
title: Lync Server 2013： 設定 Windows 8 的虛擬智慧卡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>設定 Windows 8 搭配 Lync Server 2013 使用虛擬智慧卡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-03_

要考慮部署雙因素驗證和智慧卡技術時的一個因素是實作的成本。 Windows 8 提供了數個新的安全性功能，且下方其中的最重要的新功能為虛擬智慧卡的支援。

針對配備信任平台模組 (TPM) 晶片符合規格 1.2 版的電腦，組織現在可以取得的優點智慧卡登入但不進行任何額外的投資的硬體。 如需詳細資訊，請參閱在 Windows 8 與使用虛擬智慧卡[https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>若要設定 Windows 8 的虛擬智慧卡

1.  使用已啟用 Lync 之使用者的認證，Windows 8 電腦登入。

2.  在 Windows 8 的 [開始] 畫面上，將游標移至螢幕的右下角。

3.  選取 [**搜尋**] 選項，然後搜尋**命令提示字元**。

4.  在**命令提示字元處**上, 按一下滑鼠右鍵，然後選取 [**以管理員身分執行**。

5.  開啟受信任的平台模組 (TPM) 管理主控台執行下列命令：
    
        Tpm.msc

6.  從 [TPM 管理] 主控台中，確認您 TPM 規格版本至少 1.2
    
    <div>
    

    > [!NOTE]  
    > 如果您收到表示找不到相容信任平台模組 (TPM)] 對話方塊，請確認電腦沒有相容的 TPM 模組，而且它已啟用系統 bios。

    
    </div>

7.  關閉 TPM 管理主控台

8.  從命令提示字元處，建立新虛擬智慧卡使用下列命令：
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 若要建立虛擬智慧卡時，請提供自訂的 pin 碼值，請改為使用 /pin 提示。

    
    </div>

9.  在命令提示字元中，開啟 [電腦管理] 主控台執行下列命令：
    
        CompMgmt.msc

10. 在 [電腦管理] 主控台中，選取 [**裝置管理**]。

11. 展開 [**智慧卡讀取者**]。

12. 請確認已成功建立新的虛擬智慧卡讀取。

</div>

</div>

<span> </span>

</div>

</div>

</div>

