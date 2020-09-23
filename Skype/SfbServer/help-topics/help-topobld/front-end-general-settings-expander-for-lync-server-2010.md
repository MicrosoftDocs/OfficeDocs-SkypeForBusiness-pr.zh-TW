---
title: 前端一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 您可以編輯或設定下列屬性，以編輯前端伺服器或前端集區的屬性。 設定頁面可分成下列區段：
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219094"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>前端一般設定展開工具 (適用於 Lync Server 2010)

您可以編輯或設定下列屬性，以編輯前端伺服器或前端集區的屬性。 設定頁面可分成下列區段：

 **一般**

- **FQDN**：前端伺服器或前端集區的完整功能變數名稱。

- 選取 [ **使用所有設定的 IP 位址** ]，以使用前端伺服器或前端集區上設定的所有位址。

    > [!IMPORTANT]
    > 如果您組合前端伺服器或前端集區上的轉送伺服器，請勿選取此選項。 轉送伺服器和前端伺服器需要專用的 IP 位址，以進行通訊。

- 選取 [ **將服務使用方式限制為選取的 IP 位址** ]，然後輸入前端伺服器或前端集區的 ip 位址， **以用於與** 其他部署的通訊。 輸入 **PSTN ip 位址** 與轉送伺服器相關聯的 ip 位址。

    **功能**

- **會議**：如果部署需要會議功能，請選取此核取方塊。 會議功能包含音訊、視訊、應用程式共用、桌面共用及 Web 會議。 您將需要為此屬性頁面稍後) 中所定義的 Web 會議 (建立和關聯 [Office Web Apps Server]。

- 如果選取會議，則可以選取 [電話撥入式 (PSTN) 會議]****。 選取此核取方塊可啟用電話撥入式會議功能。

- 如果您想要部署功能，以讓 Lync Server 2013 成為使用語音 over IP (的電話語音系統，請選取 [ **企業語音** ] 核取方塊。 VoIP) 技術，包括使用轉送伺服器、PSTN 閘道及 IP-PBX （結合或獨立）根據設計和需求來部署話筒電話、SIP 主幹或公用交換電話網路 connectivity 的選項。 如需有關 Enterprise Voice 的詳細資訊，請參閱[商務用 Skype Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)的[Enterprise voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) And Plan for enterprise voice。

    **協會**

- **Sql server 儲存區**： sql SERVER 的 FQDN (，並選擇性地) 與前端伺服器或前端集區相關聯的命名實例。 您可以從清單中選取 SQL Server 儲存區，或按一下 [新增]**** 建立新的 SQL Server 儲存區

- 檔案**存放區**：在 [格式]) 中，選取 `\\<FQDN of server>\<share name>` 將充當 Lync server 2013 為複寫、會議目錄及其他用途建立及使用之共用檔案的檔案存放區位置的格式中的 [伺服器和共用 (的 FQDN。 您可以從清單中選取檔案存放區，或按一下 [新增]**** 建立新的檔案存放區。

- 選取 [ **關聯封存伺服器** ] 核取方塊，啟用此前端伺服器或前端集區的封存伺服器。 選取此核取方塊後，請從清單中選取現有的封存伺服器，或按一下 [ **新增** ] 建立新封存伺服器的定義。

- 選取 [ **關聯監控伺服器** ] 核取方塊，啟用此前端伺服器或前端集區的監控伺服器。 選取此核取方塊後，請從清單中選取現有的監控伺服器，或按一下 [ **新增** ] 建立新監控伺服器的定義。

- 選取 [ **關聯媒體元件的 Edge 集區 (** ] 核取方塊，以啟用此前端伺服器或前端集區的 edge Server。 選取此核取方塊之後，您可以從清單中選取現有的 Edge Server 或集區，或按一下 [ **新增** ] 建立新 Edge Server 或集區的定義。

  **彈性**

- 選取 [ **關聯的備份註冊區集** 區] 核取方塊，以從清單中選取要作為備份 ( 報名者的前端伺服器或前端集區，也就是在主要失敗的情況下，會將前端伺服器或前端集區指定為次要註冊機) 

- 選取 [關聯的備份登錄器集區] 並選擇備份登錄器之後，即可選取 [語音的自動容錯移轉和容錯回復]****。 您現在可以定義 [語音失敗偵測間隔 (秒)]**** 和 [語音容錯回復間隔 (秒)]**** 的數值屬性。 如需詳細資訊，請參閱＜[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)＞

  **Web 服務**

- 若要設定 [內部 Web 服務]****，您可以為 [HTTP]**** 和 [HTTPS]**** 定義 [聆聽連接埠]****。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。您也可以為 [HTTP]**** 和 [HTTPS]**** 設定 [發行的連接埠]****。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。請根據您的內部 Web 服務設定及負載平衡器的用途 (硬體負載平衡器和 DNS 負載平衡) 來調整連接埠值，以定義聆聽連接埠和發行的連接埠。

    > [!IMPORTANT]
    > 內部 Web 服務以及已定義的聆聽連接埠和發行的連接埠，適用於內部用戶端和裝置。外部用戶端和裝置使用外部 Web 服務聆聽連接埠和發行的連接埠，以及已定義的外部 Web 服務完整網域名稱 (FQDN)。

- 若要設定 [外部 Web 服務]****，您可以為 [HTTP]**** 和 [HTTPS]**** 定義 [聆聽連接埠]****。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。您也可以為 [HTTP]**** 和 [HTTPS]**** 設定 [發行的連接埠]****。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。請根據您的內部 Web 服務設定及負載平衡器的用途 (硬體負載平衡器和 DNS 負載平衡) 來調整連接埠值，以定義聆聽連接埠和發行的連接埠。

    > [!IMPORTANT]
    > 外部 Web 服務以及已定義的聆聽連接埠和發行的連接埠，適用於外部用戶端和裝置。 外部用戶端和裝置使用外部 Web 服務聆聽連接埠和發行的連接埠 (一般會由反向 Proxy 及已定義的外部 Web 服務完整網域名稱 (FQDN) 所定義)。 外部 Web 服務 FQDN 與「簡單 URL」的關聯可定義統一資源定位器 (URL) 位址，以供外部用戶端用來存取外部使用者和裝置的可用服務。 如需簡單 URL 的詳細資訊，請參閱＜[Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)＞。

  **中繼伺服器**

- 若要設定組合轉送伺服器的中繼 **伺服器** 屬性 (也就是說，在前端伺服器或前端集區上部署的轉送伺服器) ，請選取 [ **組合轉送伺服器已啟用**]。

- 若要定義組合轉送伺服器的 **聆聽埠** ，請輸入組合轉送伺服器正在接聽的 **TLS** 和 **TCP** 埠值。 根據預設，TLS 會定義為 TCP 連接埠 5067。

- 若要定義轉送伺服器的 TCP 通訊埠值，請選取 [ **啟用 TCP 埠** ] 核取方塊。 根據預設，轉送伺服器會透過 TCP 通訊協定使用傳輸層安全性 (TLS) 。 只有啟用 [啟用 TCP 連接埠] 選項時，才可以使用 TCP 連接埠。

    > [!NOTE]
    > 這是選用設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。

- 您定義與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。

    如果您有多個閘道與轉送伺服器相關聯，您可以選取要設為預設的閘道，然後按一下 [ **成為預設**]，以指定預設閘道。 如果選擇移除目前的預設閘道，請選取閘道，然後按一下 [取消預設]****。

> [!IMPORTANT]
> 如果您變更此對話方塊中的屬性，您必須在所有受影響的伺服器上發行拓撲，並執行商務用 Skype Server 部署嚮導。 在發佈新的拓撲之後，必須執行「商務用 Skype 伺服器部署」嚮導所受影響的伺服器清單，以成為成功拓撲發行摘要畫面上的連結。 如需發行已更新之拓撲的詳細資訊，請參閱＜[Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)＞。 如需商務用 Skype Server 部署嚮導的詳細資訊，請參閱 [Lync Server 系統管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。

按一下 [確定]**** 儲存並認可拓撲文件的變更。

按一下 [ **取消** ] 捨棄您的變更，並關閉前端伺服器或前端集區的 **Edit 屬性** 。

按一下 [說明]**** 閱讀此說明主題。

## <a name="see-also"></a>請參閱

[定義及設定前端集區或 Standard Edition Server](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
