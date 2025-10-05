# FHE_1.2
const hre = require("hardhat");

async function main() {
  const PrivateVoting = await hre.ethers.getContractFactory("PrivateVoting");
  const voting = await PrivateVoting.deploy();
  await voting.waitForDeployment();
  console.log(`Contrato PrivateVoting desplegado en: ${voting.target}`);
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
