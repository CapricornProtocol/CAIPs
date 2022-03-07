# CAIPs
Capricorn Improvement Proposals (CAIPs) describe standards for the Capricorn platform, including core protocol specifications, client APIs, and contract standards.

# Contributing

1. Review CAIP-0.
2. Fork the repository by clicking "Fork" in the top right.
3. Add your CAIP to your fork of the repository.
4. Submit a Pull Request to Capricorn's CAIPs repository.

Your first PR should be a first draft of the final CAIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new CAIP and assign it a number before merging it. Make sure you include a `discussions-to` header with the URL to a discussion forum or open GitHub issue where people can discuss the CAIP as a whole.

If your CAIP requires images, the image files should be included in a subdirectory of the `assets` folder for that CAIP as follow: `assets/caip-X` (for caip **X**). When linking to an image in the CAIP, use relative links such as `../assets/caip-X/image.png`.

Once your first PR is merged, we have a bot that helps out by automatically merging PRs to draft CAIPs. For this to work, it has to be able to tell that you own the draft being edited. Make sure that the 'author' line of your CAIP contains either your Github username or your email address inside <triangular brackets>. If you use your email address, that address must be the one publicly shown on your GitHub profile.

# CAIP Status Terms
* **Draft** - an CAIP that is undergoing rapid iteration and changes.
* **Last Call** - an CAIP that is done with its initial iteration and ready for review by a wide audience.
* **Accepted** - a core CAIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author. The process for Core Devs to decide whether to encode an CAIP into their clients as part of a hard fork is not part of the CAIP process. If such a decision is made, the CAIP wil move to final.
* **Final (non-Core)** - an CAIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author.
* **Final (Core)** - an CAIP that the Core Devs have decided to implement and release in a future hard fork or has already been released in a hard fork.
* **Deferred** - an CAIP that is not being considered for immediate adoption. May be reconsidered in the future for a subsequent hard fork.

