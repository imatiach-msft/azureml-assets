## Limitations

- Prior knowledge of protein structures is required.
- Currently, compounds are not generated in 3D spaces, representing a potential area for future enhancement.
- Users need to leverage wet-lab experiments to verify the generated compounds and design pipelines to determine which compound to synthesise (e.g., using molecular docking to pick up compounds with potentially good binding affinity).

## Risks and mitigations

The release of TamGen is relatively low-risk, as real-world compound design is a very complex pipeline:

- Compound design is an intricate process that extends far beyond initial generation (i.e., what TamGen works on). After a compound is generated, it undergoes rigorous filtering and selection processes to identify suitable drug candidates (e.g., enzymatic test, cellular activity test, animal test, etc.).
- TamGen incorporates an additional filter to eliminate compounds with undesired properties.
- Currently, there are already compound generation methods released, like Pocket2Mol and MoLeR. The lack of malicious outcomes stemming from the existence of these models suggests that either the synthesis knowledge firewall is sufficient to deter untoward use or that the design of compound generation is not a useful tool for malicious outcomes.

## Condition to use

The TamGen is provided “as is”, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. The TamGen is aimed to facilitate drug discovery research and is not suitable for any other use, including clinical applications. Compounds generated by TamGen shall be subject to a rigorous filtering and selection process to identify suitable drug candidates. Users shall independently assess and test the risks of the TamGen in generating specific compounds, ensure the responsible use of AI technology, including but not limited to the development and integration risk mitigation measures, and comply with all applicable laws and regulations in all applicable jurisdictions. Users shall assume all liability under any theory of liability, whether in contract, torts, regulatory, negligence, products liability, or otherwise, associated with the use of the TamGen and any inputs and outputs thereof. The TamGen output may contain inaccuracies, and users are responsible for determining the accuracy of any outputs generated by TamGen in relation to its intended use.
