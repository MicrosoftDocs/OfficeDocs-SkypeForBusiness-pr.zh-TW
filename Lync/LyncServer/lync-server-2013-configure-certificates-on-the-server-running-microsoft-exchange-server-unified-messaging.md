---
title: Lync Server 2013：在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證
description: Lync Server 2013：在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564399"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

如果您已部署 Exchange 整合通訊 (UM) （如規劃檔中的「 [在 Lync Server 2013 中規劃 exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 」中所述），且您想要將 exchange um 功能提供給組織中的 Enterprise Voice 使用者，您可以使用下列程式在執行 Exchange um 的伺服器上設定憑證。

<div>


> [!IMPORTANT]  
> 針對內部憑證，執行 Lync Server 2013 的伺服器和執行 Microsoft Exchange 的伺服器必須具有相互信任的根信任授權憑證。 憑證授權單位單位 (CA) 可以相同或不同的憑證授權單位單位，只要伺服器在其受信任的根授權憑證存放區中註冊了憑證授權單位的根憑證。



</div>

必須將 Exchange 伺服器設定為使用伺服器憑證，才能連線至 Lync Server 2013：

1.  下載 Exchange Server 的 CA 憑證。

2.  安裝 Exchange Server 的 CA 憑證。

3.  確認 CA 在 Exchange Server 的受信任的根 CA 清單中。

4.  建立 Exchange Server 的憑證要求並安裝憑證。

5.  指派 Exchange Server 的憑證。

<div>

## <a name="to-download-the-ca-certificate"></a>若要下載 CA 憑證

1.  在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，輸入 **Http:// \<name of your Issuing CA Server\> /Certsrv**，然後按一下 **[確定]**。

2.  在 **[選取工作]** 下方，按一下 **[下載 CA 憑證、憑證鏈結或 CRL]**。

3.  在 [ **下載 Ca 憑證、憑證鏈或 CRL**] 底下，選取 [ **編碼方式為 64**]，然後按一下 [ **下載 CA 憑證**]。
    
    <div>
    

    > [!NOTE]  
    > 您也可以在此步驟 (DER) 編碼中指定可辨識的編碼規則。 如果您選取 DER 編碼，此程序下一個步驟中以及<STRONG>「若要安裝 CA 憑證」</STRONG>步驟 10 中的檔案類型會是 .p7b，而非 .cer。

    
    </div>

4.  在 **[檔案下載]** 對話方塊中，按一下 **[儲存]**，然後將檔案儲存到伺服器的硬碟上 (視您在上一個步驟中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>若要安裝 CA 憑證

1.  在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，然後在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**，以開啟 Microsoft Management Console (MMC) 。

2.  在 **[檔案]** 功能表中，按一下 **[新增/移除嵌入式管理單元]**，然後按一下 **[新增]**。

3.  在 **[新增獨立嵌入式管理單元]** 方塊中，按一下 **[憑證]**，然後按一下 **[新增]**。

4.  在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。

5.  在 [ **選取電腦** ] 對話方塊中，確認已選取 [ **本機電腦： (執行此主控台的電腦) ** ] 核取方塊，然後按一下 **[完成]**。

6.  按一下 **[關閉]**，然後按一下 **[確定]**。

7.  在主控台樹狀目錄中，依序展開 **[憑證 (本機電腦)]** 和 **[信任的根憑證授權]**，然後按一下 **[憑證]**。

8.  以滑鼠右鍵按一下 **[憑證]**，按一下 **[所有工作]**，再按一下 **[匯入]**。

9.  按 **[下一步]**。

10. 按一下 **[瀏覽]**，找出檔案，然後按 **[下一步]** (視您在 **「若要下載 CA 憑證」** 步驟 3 中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。

11. 按一下 **[將所有憑證放入以下的存放區]**。

12. 按一下 **[瀏覽]**，然後選取 **[受信任的根憑證授權單位]**。

13. 按 **[下一步]** 以驗證設定，然後按一下 **[完成]**。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>若要確認 CA 是否在受信任的根 CA 清單中

1.  在執行 Exchange UM 的伺服器上，于 MMC 中展開 [ **憑證 (本機電腦]) **中，展開 [ **受信任的根憑證授權**單位]，然後按一下 [ **憑證**]。

2.  在詳細資料窗格中，確認您的 CA 位於受信任的 CA 清單上。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>設定 Exchange Server 2013 UM 與 Lync Server

1.  如需詳細資訊，請參閱 Exchange Server 檔中的「整合 Exchange 2013 UM 與 Lync Server」 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>若要在 Exchange Server 2007 (SP1) 上建立憑證要求及安裝憑證

1.  在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，輸入 **Http:// \<**name of your Issuing CA Server**\> /Certsrv**，然後按一下 **[確定]**。

2.  在 **[選取工作]** 下，按一下 **[要求憑證]**。

3.  在 **[要求憑證]** 下，按一下 **[進階憑證要求]**。

4.  在 **[進階憑證要求]** 下，按一下 **[建立並送出要求至此 CA]**。

5.  在 **[進階憑證要求]** 下，選取 **[Web 伺服器]** 或針對伺服器驗證設定的另一個伺服器憑證範本。

6.  在 [ **離線範本識別資訊**] 底下的 [ **名稱** ] 方塊中，輸入 Exchange 伺服器的完整功能變數名稱 (FQDN) 。
    
    <div>
    

    > [!NOTE]  
    > 您必須輸入 Exchange Server 的 FQDN，才能夠進行通訊。

    
    </div>

7.  在 **[金鑰選項]** 下，按一下 **[將憑證存放在本機電腦憑證存放區]** 核取方塊。

8.  按一下網頁下方的 **[送出]** 按鈕。

9.  在開啟並要求確認的對話方塊中，按一下 **[是]**。

10. 在 [已發出憑證] 頁面的 **[已發出憑證]** 下，按一下 **[安裝這個憑證]**。

11. 在開啟並要求確認的對話方塊中，按一下 **[是]**。

12. 確認顯示「您的新憑證已經安裝成功」訊息。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>若要在 Exchange Server 2010 上建立憑證

1.  以適當的使用者權限登入執行 Exchange UM 的伺服器。 如需詳細資訊，請參閱的「用戶端存取許可權」 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。

2.  參閱下列程序以建立憑證：
    
    1.  「建立新的 Exchange 憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  「匯入 Exchange 憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 對於憑證的 <STRONG>[主體名稱]</STRONG>，您必須輸入 Exchange Server 的 FQDN，才能夠進行通訊。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>若要在 Exchange Server 2007 (SP1) 上指派憑證

1.  在執行 Exchange UM 的伺服器上，開啟 [MMC]。

2.  在主控台樹狀目錄中，展開 **[個人]**，然後按一下 **[憑證]**。

3.  在詳細資料窗格中，確認有顯示個人憑證。

4.  按兩下憑證以閱讀其詳細資料，並確認其有效。
    
    <div>
    

    > [!NOTE]  
    > 可能需要幾分鐘，才會顯示憑證是有效的。

    
    </div>

5.  重新啟動 Microsoft Exchange Unified Messaging 服務。
    
    <div>
    

    > [!NOTE]  
    > 執行 Exchange Server 2007 SP1 Unified Messaging 的伺服器會自動擷取正確的憑證。

    
    </div>

6.  開啟 [事件檢視器] 並尋找事件識別碼 1112，此事件識別碼會指定執行 Exchange Server 2007 SP1 Unified Messaging 之伺服器所擷取的憑證。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>若要在 Exchange Server 2010 上指派憑證

1.  以適當的使用者權限登入執行 Exchange UM 的伺服器。 如需詳細資訊，請參閱的「用戶端存取許可權」 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。

2.  如需指派憑證的程式，請參閱的「將服務指派給憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

