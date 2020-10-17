---
title: Lync Server 2013：設定虛擬智慧卡的 Windows 8
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
ms.openlocfilehash: 09f6c33ab9619e7a6b168e5d552ac13d84343c3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502060"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>設定使用虛擬智慧卡搭配 Lync Server 2013 的 Windows 8

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-03_

部署雙因素驗證和智慧卡技術時，要考慮的一個因素是實施成本。 Windows 8 提供許多新的安全性功能，其中一個最有意思的新功能是支援虛擬智慧卡。

針對配備受信任平臺模組的電腦 (符合規格版本1.2 的 TPM) 晶片，組織現在可以取得智慧卡登入的優勢，而不需要在硬體上進行任何額外的投資。 如需詳細資訊，請參閱搭配 Windows 8 使用虛擬智慧卡 [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) 。

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>設定虛擬智慧卡的 Windows 8

1.  使用啟用 Lync 功能之使用者的認證登入 Windows 8 電腦。

2.  在 [Windows 8 開始] 畫面上，將游標移至螢幕的右下角。

3.  選取 [ **搜尋** ] 選項，然後搜尋 [ **命令提示**字元]。

4.  在 **命令提示**字元上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。

5.  執行下列命令，以 (TPM) 管理主控台開啟受信任的平臺模組：
    
        Tpm.msc

6.  在 [TPM 管理主控台] 中，確認您的 TPM 規格版本至少是1。2
    
    <div>
    

    > [!NOTE]  
    > 如果您收到的對話方塊指出無法找到相容的信任平臺模組 (TPM) ，請確認該電腦具有相容的 TPM 模組，且已在系統 BIOS 中啟用。

    
    </div>

7.  關閉 TPM 管理主控台

8.  在命令提示字元處，使用下列命令建立新的虛擬智慧卡：
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 若要在建立虛擬智慧卡時提供自訂 PIN 碼值，請改用/pin prompt。

    
    </div>

9.  在命令提示字元中執行下列命令，以開啟 [電腦管理] 主控台：
    
        CompMgmt.msc

10. 在 [電腦管理] 主控台中，選取 [ **裝置管理**]。

11. 展開 [ **智慧卡讀取器**]。

12. 確認已成功建立新的虛擬智慧卡讀取器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

