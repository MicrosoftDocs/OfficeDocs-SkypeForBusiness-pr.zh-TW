---
title: Lync Server 2013：在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

如果您已部署 Exchange 整合訊息（UM），請參閱規劃檔中的[Lync Server 2013 規劃 Exchange 整合訊息整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)，以及您想要為貴組織中的企業語音使用者提供 exchange um 功能，您可以使用下列程式來設定執行 Exchange um 之伺服器上的憑證。

<div>


> [!IMPORTANT]  
> 對於內部憑證，執行 Lync Server 2013 的伺服器以及執行 Microsoft Exchange 的伺服器都必須擁有互相信任的根信任頒發機構憑證。 只要伺服器已在其受信任的根授權憑證存放區中註冊認證機構的根憑證，憑證授權單位（CA）就可以是相同或不同的憑證授權單位。



</div>

Exchange 伺服器必須使用伺服器憑證進行設定，才能連線至 Lync Server 2013：

1.  下載 Exchange 伺服器的 CA 憑證。

2.  安裝 Exchange 伺服器的 CA 憑證。

3.  確認 CA 位於 Exchange 伺服器的根信任 Ca 清單中。

4.  建立 Exchange 伺服器的憑證要求並安裝證書。

5.  指派 Exchange 伺服器的憑證。

<div>

## <a name="to-download-the-ca-certificate"></a>下載 CA 憑證

1.  在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入**發證 CA\>伺服器\</Certsrv 的 HTTP://名稱**，然後按一下 **[確定]**。

2.  在 [**選取任務**] 底下，按一下 [**下載 CA 憑證、憑證鏈或 CRL**]。

3.  在 [**下載 Ca 憑證、憑證連結或 CRL**] 底下，選取 [**編碼方法至基本 64**]，然後按一下 [**下載 CA 憑證**]。
    
    <div>
    

    > [!NOTE]  
    > 您也可以在此步驟指定可分辨編碼規則（DER）編碼。 如果您選取 [DER 編碼]，此程式的下一個步驟中和<STRONG>安裝 CA 憑證</STRONG>的步驟10中的檔案類型是. p7b （而不是 .cer）。

    
    </div>

4.  在 [檔案**下載**] 對話方塊中，按一下 [**儲存**]，然後將檔案儲存到伺服器上的硬碟。 （根據您在上一個步驟中選取的編碼，該檔案將會有 .cer 或. p7b 檔案副檔名。）

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>若要安裝 CA 憑證

1.  在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**。

2.  **在 [檔案**] 功能表上，按一下 [**新增/移除管理單元**]，然後按一下 [**新增**]。

3.  在 [**新增獨立的管理單元**] 方塊中，按一下 [**憑證**]，然後按一下 [**新增**]。

4.  在 [**憑證管理單元**] 對話方塊中，按一下 [**電腦帳戶**]，然後按一下 **[下一步]**。

5.  在 [**選取電腦**] 對話方塊中，確認已選取 [**本機電腦（執行此主控台的電腦）** ] 核取方塊，然後按一下 **[完成]**。

6.  按一下 [**關閉**]，然後按一下 **[確定]**。

7.  在主控台樹中，展開 [**憑證（本機電腦）**]，展開 [**信任的根憑證授權單位**]，然後按一下 [**憑證**]。

8.  以滑鼠右鍵按一下 [**憑證**]，按一下 [**所有任務**]，然後按一下 [匯**入**]。

9.  按一下 **[下一步]**。

10. 按一下 **[流覽]** 找出檔案，然後按一下 **[下一步**]。 （檔案將會有 .cer 或. p7b 副檔名，視您在**下載 CA 憑證**的步驟3中所選取的編碼而定。

11. 按一下 **[將所有憑證放入下列存放區**]。

12. 按一下 **[流覽]**，然後選取 [**信任的根憑證授權單位**]。

13. 按一下 **[下一步**] 驗證設定，然後按一下 **[完成]**。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>確認 CA 位於信任的根 Ca 清單中

1.  在執行 Exchange UM 的伺服器上，在 MMC 中展開 **[憑證（本機電腦）**]，展開 [**信任的根憑證授權單位**]，然後按一下 [**憑證**]。

2.  在 [詳細資料] 窗格中，確認您的 CA 位於信任的 Ca 清單中。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>若要將 Exchange Server 2013 UM 設定為使用 Lync Server

1.  如需詳細資訊，請參閱 Exchange Server 檔中的「整合與 Lync Server 的 Exchange [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)2013 UM」。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>在 Exchange Server 2007 （SP1）上建立憑證要求並安裝證書

1.  在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入發證 CA 伺服器**\>/certsrv**的**HTTP://\<** 名稱，然後按一下 **[確定]**。

2.  按一下 [**選取任務**] 底下的 [**要求憑證**]。

3.  在 [**要求證書**] 底下，按一下 [**高級證書要求**]。

4.  在 [**高級憑證要求**] 底下，按一下 [**建立並提交此 CA 的要求**]。

5.  在 [**高級證書申請**] 底下，選取 [ **Web 服務器**] 或 [其他設定為伺服器驗證的伺服器憑證範本]。

6.  在 [**離線範本的識別資訊**] 底下的 [**名稱**] 方塊中，輸入 Exchange 伺服器的完整功能變數名稱（FQDN）。
    
    <div>
    

    > [!NOTE]  
    > 您必須輸入 Exchange 伺服器的 FQDN，才能進行通訊。

    
    </div>

7.  在 [**金鑰選項**] 底下，按一下 [**將憑證儲存在本機電腦憑證存放區**] 核取方塊。

8.  按一下網頁底部的 [Submit] （**提交**）按鈕。

9.  在開啟要求確認的對話方塊中，按一下 **[是**]。

10. 在 [頒發的憑證] 頁面上的 [**頒發的憑證**] 底下，按一下 [**安裝此憑證**]。

11. 在開啟要求確認的對話方塊中，按一下 **[是**]。

12. 確認出現「您的新憑證已成功安裝」訊息。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上建立憑證

1.  以適當的使用者權利登入執行 Exchange UM 的伺服器。 如需詳細資訊，請參閱「用戶端[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)存取許可權」。

2.  請參閱下列程式來建立證書：
    
    1.  「建立新的 Exchange 憑證」[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  「匯入 Exchange 憑證」[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 針對證書<STRONG>受領人名稱</STRONG>，您必須輸入 Exchange 伺服器的 FQDN，才能使用通訊。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>在 Exchange Server 2007 （SP1）上指派憑證

1.  在執行 Exchange UM 的伺服器上，開啟 [MMC]。

2.  在主控台樹中，展開 [**個人**]，然後按一下 [**憑證**]。

3.  在 [詳細資料] 窗格中，確認已顯示 [個人憑證]。

4.  按兩下憑證以閱讀其詳細資料，並確認它是有效的。
    
    <div>
    

    > [!NOTE]  
    > 認證可能需要幾分鐘的時間，才會顯示為有效。

    
    </div>

5.  重新開機 Microsoft Exchange 整合訊息服務。
    
    <div>
    

    > [!NOTE]  
    > 運行 Exchange Server 2007 SP1 整合通訊的伺服器會自動檢索正確的憑證。

    
    </div>

6.  開啟 [事件檢視器] 並尋找事件 ID 1112，該事件會指定伺服器執行 Exchange Server 2007 SP1 之統一通訊已檢索的憑證。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>在 Exchange Server 2010 上指派憑證

1.  以適當的使用者權利登入執行 Exchange UM 的伺服器。 如需詳細資訊，請參閱「用戶端[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)存取許可權」。

2.  如需指派證書的程式，請參閱「指派服務給證書」 [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

