# Life Ledger: The Photo Journal Application

## 📌 The Problem
Standard photo galleries capture the image but lose the context, while traditional text diaries lack visual depth. Life Ledger bridges this gap by providing a unified platform where users can securely bind their written memories to specific photographs, creating a rich, chronological, and cloud-backed timeline of their life.

## ✨ Core Features
* **Rich Media Entries:** Create, edit, and manage journal entries that seamlessly integrate text narratives with photographic memories.
* **Cloud Sync:** Ensures that no memory is ever lost to a broken or upgraded device by securely syncing all entries to the cloud in real-time.
* **Optimized Feed:** Smoothly scroll through years of heavy, photo-rich journal entries without lag or memory crashes, thanks to efficient view recycling.
* **Secure Storage:** Leverages robust backend infrastructure to isolate and protect user-generated content.

## 🛠 Tech Stack
* **Languages:** Java, Kotlin (Demonstrating strong JVM interoperability)
* **UI Architecture:** Android SDK, RecyclerView
* **Database:** Firebase Firestore (NoSQL Document Store)
* **Backend Services:** Appwrite (Authentication & Object Storage)

## 🏗 Architecture & Logic
Life Ledger is built with a focus on separating the UI from the complex data-handling layers, utilizing two distinct backend services:
1. **The Data Layer (Firestore):** Firebase Firestore is utilized to store the metadata of the journal entries (timestamp, journal text, image URLs). Its real-time synchronization capabilities ensure the app's state is always up-to-date.
2. **The Media Layer (Appwrite):** Appwrite handles the heavy lifting of storing and serving the actual image files (blobs), keeping the Firestore database lightweight and optimized for text queries.
3. **The Presentation Layer (RecyclerView):** To handle potentially hundreds of image-heavy journal entries, the app implements the `RecyclerView` pattern. This ensures that only the UI elements currently visible on the screen are rendered in memory, drastically reducing the application's RAM footprint and preventing `OutOfMemory` exceptions.

## 🚀 Installation & Setup

### Prerequisites
* Android Studio (latest version)
* Java Development Kit (JDK) 11+
* A Firebase Project configured for Android
* An Appwrite Project (Cloud or Self-Hosted)

